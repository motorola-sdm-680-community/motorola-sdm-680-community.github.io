---
title: "Custom ROM Flashing Guide for Motorola G32(devon), G42(hawao) and G52(rhode)"
meta-title: "Custom ROM Flashing Guide for Motorola G32(devon), G42(hawao) and G52(rhode)"
description: "Flashing guide for Motorola devices with Snapdragon 680 chipset like G32(codename devon), G42(codename hawao) and G52(codename rhode)"
date: 2023-12-01T05:00:00Z
image: "/images/image-placeholder.png"
categories: ["Flashing", "Custom ROM", "Beginner Guide"]
author: "Motorola Snapdragon 680 Community"
tags: ["Custom ROM", "ROMs"]
draft: false
type: blog
---

[//]: # (TODO: Make it more detailed for noobs)
[//]: # (TODO: Embed Youtube Tutorial)

## Required files

Download (boot.img, vendor_boot.img & dtbo.img) from the links below for your devices

<div class="inline-flex flex-col md:flex-row mx-auto gap-4">
  {{< button label="Devon (Moto G32)" link="https://t.me/sdm680_moto/50929" >}}
  {{< button label="Hawao (Moto G42)" link="https://t.me/motog52custom/20" >}}
  {{< button label="Rhode (Moto G52)" link="https://t.me/g52com/38442/71520" >}}
</div>

## Instructions

### From Stock ROM to Custom ROM

Now put boot, vendor_boot & dtbo in platform tool after that connect your device with pc in fastboot mode then open CMD inside platform tool and run these commands one by one given below

```bash
fastboot flash boot boot.img

fastboot flash vendor_boot vendor_boot.img

fastboot flash dtbo dtbo.img
```

#### After flashing boot, vendor_boot & dtbo successfully follow given steps below

- Boot to Recovery
- Format Data
- Flash Copy Partition zip (Download here)
- Reboot to Recovery 
- Flash Rom
- Reboot to Recovery again 
- Flash Gapps (if you're flashing vanilla build)
- Format Data 
- Reboot to System 

<hr>

### From any Custom ROM to Another Custom ROM

- Boot to recovery (comes with roms inbuilt or TWRP)
- Format Data
- Flash ROM
- Reboot to Recovery 
- Flash Gapps (If you're flashing vanilla build)
- Format Data
- Reboot to System