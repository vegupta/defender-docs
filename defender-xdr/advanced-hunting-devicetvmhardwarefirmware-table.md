---
title: DeviceTvmHardwareFirmware table in the advanced hunting schema
description: Learn about the DeviceTvmHardwareFirmware table in the advanced hunting schema, which includes information on devices like processor, BIOS, and others, as checked in threat and vulnerability management in Microsoft Defender XDR.
search.appverid: met150
ms.service: defender-xdr
ms.subservice: adv-hunting
f1.keywords: 
  - NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
- m365-security
- tier3
ms.custom: 
- cx-ti
- cx-ah
ms.topic: reference
ms.date: 12/29/2023
---

# DeviceTvmHardwareFirmware

[!INCLUDE [Microsoft Defender XDR rebranding](../includes/microsoft-defender.md)]


**Applies to:**
- Microsoft Defender XDR

> [!IMPORTANT]
> Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

The `DeviceTvmHardwareFirmware` table in the advanced hunting schema contains hardware and firmware information of devices as checked by [Microsoft Defender Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). The information includes the system model, processor, and BIOS, among others.

For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).

| Column name | Data type | Description |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Unique identifier for the device in the service |
| `DeviceName` | `string` | Fully qualified domain name (FQDN) of the device |
| `ComponentType` | `string` | Type of hardware or firmware component |
| `Manufacturer` | `string` | Manufacturer of hardware or firmware component |
| `ComponentName` | `string` | Name of hardware or firmware component |
| `ComponentFamily` | `string` | Component family or class, a grouping of components that have similar features or characteristics as determined by the manufacturer |
| `ComponentVersion` | `string` | Component version (for example, BIOS version) |
| `AdditionalFields` | `dynamic` | Additional information about the components in JSON array format |

You can try the following sample queries to use the information available in the `DeviceTvmHardwareFirmware` table:

```kusto
// Count the number of Lenovo devices
DeviceTvmHardwareFirmware
| where ComponentType == "Hardware" and Manufacturer == "lenovo"
| summarize count()
```

```kusto
// Find all devices with a specific BIOS version, replace ComponentVersion with what you are looking for
DeviceTvmHardwareFirmware
| where ComponentType == "Bios" and ComponentVersion contains "N2VET29W"
|project DeviceId, DeviceName
```

## Related topics

- [Proactively hunt for threats](advanced-hunting-overview.md)
- [Learn the query language](advanced-hunting-query-language.md)
- [Understand the schema](advanced-hunting-schema-tables.md)
- [Apply query best practices](advanced-hunting-best-practices.md)
- [Overview of Microsoft Defender Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
[!INCLUDE [Microsoft Defender XDR rebranding](../includes/defender-m3d-techcommunity.md)]
