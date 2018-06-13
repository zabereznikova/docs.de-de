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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c5bc63da7ebe86b653c9bef7caeb1cf28d3a7f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450049"
---
# <a name="osinfo-structure"></a>OSINFO-Struktur
Enthält Details über das Betriebssystem für eine Assembly oder ein Modul.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwOSPlatformId`|Einer der Bezeichnerwerte, die durch die Microsoft Windows-Plattform-Funktion definierten `GetVersionEx`. Die folgenden Werte werden unterstützt:<br /><br /> -VER_PLATFORM_WIN32s, oder 0 x 0000, um Microsoft Windows 3.1 anzugeben.<br />-VER_PLATFORM_WIN32_WINDOWS, oder 0 x 0001, Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von ihnen abgeleitet wurde.<br />-VER_PLATFORM_WIN32_NT, oder 0 x 0010, Windows NT oder Betriebssysteme anzugeben, die von der sie abgeleitet wurde.|  
|`dwOSMajorVersion`|Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
|`dwOSMinorVersion`|Die Nebenversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 `OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete der Microsoft Windows-Plattform-Funktion `GetVersionEx`. Diese Struktur wird von der ASSEMBLYMETADATA-Struktur an, dass die Betriebssystem-Unterstützung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
