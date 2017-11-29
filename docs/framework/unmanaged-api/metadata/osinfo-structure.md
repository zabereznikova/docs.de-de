---
title: OSINFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 700e9bcfe33e5be3725bd24b212b3a77ad139b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 `OSINFO`basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete der Microsoft Windows-Plattform-Funktion `GetVersionEx`. Diese Struktur wird von der ASSEMBLYMETADATA-Struktur an, dass die Betriebssystem-Unterstützung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
