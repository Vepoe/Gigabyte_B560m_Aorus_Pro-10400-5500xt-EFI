Gigabyte_B560m_Aorus_Pro-10400-5500xt EFI
==========================================================================

配置
---------------------------------------------------------------------------
<table>    
<tr>
<th text-align="left">硬件</th>
<th text-align="left">型号</td>
</tr>
    
<tr>
<th text-align="left" rowspan="4">主板:</th>
</tr>
    
<tr>
<td text-align="left">技嘉Gigabyte_B560m_Aorus_Pro</td>
</tr>

<tr>
<td text-align="left" >声卡:瑞昱ALC897</td>
</tr>

<tr>
<td text-align="left">网卡:Intel® Ethernet Controller I225-V</td>
</tr>

<tr>
<th text-align="left">CPU:</th>
<td text-align="left">Intel I5-10400</td>
</tr>
    
<tr>
<th text-align="left">显卡:</th>
<td text-align="left">蓝宝石Sapphire 5500xt</td>
</tr>
    
<tr>
<th text-align="left">内存:</th>
<td text-align="left">英睿达crucial 4 x 8GB c9bjz,超频到3600</td>
</tr>
    
<tr>
<th text-align="left" rowspan="3">固态硬盘:</th>
</tr>
    
<tr>
<td text-align="left">西数黑盘WD SN750 256GBb(装Win)</td>
</tr>

<tr>
<td text-align="left">铠侠KIOXIA RC10 500GB(装Mac)</td>
</tr>

<tr>
<th text-align="left">WIFI和蓝牙:</th>
<td text-align="left">博通 BCM94360CD</td>
</tr>

</table>  


系统信息
---------------------------------------------------------------------------
* MacOS:BigSur 11.2.3
* SMBIOS:iMac20,1

EFI
---------------------------------------------------------------------------
* OpenCore Version 0.6.7
   * ACPI
      * SSDT-AWAC.aml
      * SSDT-EC-USBX-DESKTOP.aml
         * ACPI路径重名为：`PC00.LPCB` 修复睡眠问题
      * SSDT-PLUG.aml
      * SSDT-RHUB.aml
         * ACPI路径重名为：`PC00.XHCI.RHUB` 修复USB不能驱动
      * SSDT-RX5500XT-Version1.0.aml
         * ACPI路径重名为：`PC00.PEG1.PEGP`优化5500xt性能
   * DeviceProperties
      * PciRoot(0x0)/Pci(0x1C,0x0)/Pci(0x0,0x0)
         * device-id  `F2150000` 配合fakeid驱动i225-v
      * PciRoot(0x0)/Pci(0x2,0x0) `开启核显加速`
   * Drives
      * HfsPlus.efi
      * OpenCanopy.efi
      * OpenRuntime.efi
   * Kexts
      * Lilu
      * VirtualSMC
      * AirportBrcmFixup
      * VooDooHDA
      * BrcmBluetoothInjector
      * DAGPM
      * FakePCIID
      * FakePCIID_Intel_I225-V
      * WhateverGreen
      * NVMeFix(v1.0.5)
      * USBPorts(定制)
      * CtlnaAHCIPort

正常工作
---------------------------------------------------------------------------
- cpu睿频
- 隔空投送、接力
- 万能声卡驱动声卡，applealc-1.5.8目前不支持500系列主版，编译报错无法驱动
- intel i225-v网卡
- wifi
- 蓝牙
- 所有usb插口

未工作
---------------------------------------------------------------------------
- oc引导主题
- hackintool无法查看`cfglock`是否关闭
- 睡眠和唤醒未测试

成果
---------------------------------------------------------------------------
![系统信息](https://user-images.githubusercontent.com/58576156/113425972-55ca4a00-9405-11eb-87e8-2a579d550f43.png)
![cpu](https://user-images.githubusercontent.com/58576156/113425398-5c0bf680-9404-11eb-921c-97c30826c709.png)
![核显加速](https://user-images.githubusercontent.com/58576156/113426032-72668200-9405-11eb-926d-34d926454902.png)
![OpenCL](https://user-images.githubusercontent.com/58576156/113425405-6201d780-9404-11eb-8d37-15569bb8670e.png)
![Metal](https://user-images.githubusercontent.com/58576156/113425411-64fcc800-9404-11eb-8dfd-691527f4c80e.png)
![睿频](https://user-images.githubusercontent.com/58576156/113426271-cfface80-9405-11eb-9e33-df1704b05c36.png)






