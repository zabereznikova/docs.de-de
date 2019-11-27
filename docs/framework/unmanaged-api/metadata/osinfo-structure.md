---
title: OSINFO-Struktur
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 89111bf7eb03d20c2010c7a20c4cd055c2a021e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430736"
---
# <a name="osinfo-structure"></a>OSINFO-Struktur
Enthält Details zum Betriebssystem für eine Assembly oder ein Modul.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwOSPlatformId`|Einer der Bezeichnerwerte, die von der Microsoft Windows-Platt Form Funktion `GetVersionEx`definiert werden. Die folgenden Werte werden unterstützt:<br /><br /> -VER_PLATFORM_WIN32s oder 0x0000 zum Angeben von Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS oder 0x0001, um Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von Ihnen abgeleitet wurden.<br />-VER_PLATFORM_WIN32_NT oder 0x0010, um Windows NT oder Betriebssysteme anzugeben, die davon abgeleitet wurden.|  
|`dwOSMajorVersion`|Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
|`dwOSMinorVersion`|Die neben Version des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 `OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen der Funktion `GetVersionEx`der Microsoft Windows-Plattform verwendet wird. Diese Struktur wird von der ASSEMBLYMETADATA-Struktur verwendet, um die Betriebssystemunterstützung anzugeben.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
