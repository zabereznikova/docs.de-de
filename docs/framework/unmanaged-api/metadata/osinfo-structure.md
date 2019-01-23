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
ms.openlocfilehash: abab67f28a5fabfc6c348af6b8b502b46510d460
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548754"
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
|`dwOSPlatformId`|Die ID-Werte, die von der Microsoft Windows-Plattform-Funktion definiert `GetVersionEx`. Die folgenden Werte werden unterstützt:<br /><br /> -VER_PLATFORM_WIN32s, oder 0 x 0000, Microsoft Windows 3.1 angeben.<br />-VER_PLATFORM_WIN32_WINDOWS, oder 0 x 0001, die Angabe von Windows 95, Windows 98 oder Betriebssysteme, die von ihnen abgeleitet.<br />-VER_PLATFORM_WIN32_NT, oder 0 x 0010, die Angabe von Windows NT oder Betriebssysteme, die von ihm abgeleitet.|  
|`dwOSMajorVersion`|Die Hauptversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.|  
|`dwOSMinorVersion`|Die Nebenversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 `OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete die Microsoft Windows-Plattform-Funktion `GetVersionEx`. Diese Struktur wird durch die ASSEMBLYMETADATA-Struktur verwendet, um die betriebssystemunterstützung anzugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
