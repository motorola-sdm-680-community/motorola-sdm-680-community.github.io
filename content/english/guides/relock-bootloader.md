---
title: 'Bootloader Relocking Guide for Motorola G32(devon), G42(hawao) and G52(rhode)'
meta-title: 'Bootloader Relocking Guide for Motorola G32(devon), G42(hawao) and G52(rhode)'
description: 'Bootloader Relocking Guide for Motorola devices with Snapdragon 680 chipset like G32(codename devon), G42(codename hawao) and G52(codename rhode)'
data: '2023-12-13T23:07:19+05:30'
image: "/images/image-placeholder.png"
author: "Motorola Snapdragon 680 Community"
categories: []
tags: []
draft: false
type: blog
---

## Disclaimer

{{< notice "warning" >}}

**DO NOT SKIP, CHANGE OR MODIFY ANY OF THE STEPS, THERE'S 
HIGH POSSIBILITY OF HARD BRICKING YOUR DEVICE WITH NO WAY TO RECOVER IF YOU MISS ANY STEP.**

There are other methods to flash firmware and relock but this is what I use and trust.

{{< /notice >}}

## Instructions

So the first order of step would be to go to fastboot mode and find out the software channel of the device
You can achieve this by the following command:-

```bash
fastboot getvar ro.carrier
```

It'll return the region of your device, In my case it was retin

```bash
(bootloader) ro.carrier: retin
```


Now we will go to the below link,

{{<button label="Firmware" link="https://mirrors.lolinet.com/firmware/motorola/rhode/official/">}}

And download the latest available firmware for your device and software channel, Make sure to download the correct region only

After downloading it extract the zip


Then download tinyfastbootscript (en version)

{{<button label="TinyFastbootScript" link="https://mirrors.lolinet.com/software/windows/TinyFastbootScript/">}}

After downloading extract the tinyfastbootscript zip and move the two files inside to the extracted stock rom folder


After that is complete connect your device in fastboot mode then open the flash.bat program inside the stock rom folder

On initial setup it'll ask for fastboot version (select the default moto fastboot, Option 1)

Then it'll ask for flashing then select option 5 (flash full firmware with factory reset)

After firmware is flashed reboot device wait till it reaches hello screen on setup

{{< notice "warning" >}}

Again, Only do it when you're 100% sure the firmware is of correct region and latest available otherwise you'll have a unrecoverable hard brick.

{{< /notice >}}

Then you can go into fastboot to relock the bootloader using the following command.

```bash
fastboot oem lock
```

It'll relock and do factory reset, After that you can reboot and enjoy.

## Results

{{< gallery dir="images/relock-bootloader" zoomable="true" command="Fit" >}}