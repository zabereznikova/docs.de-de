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
ms.openlocfilehash: 49e29cc0367d5162dffcd641b163fd7b9a56ffd0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672889"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`dwOSPlatformId`|Einer der Bezeichnerwerte, der durch die Microsoft Windows-Platt Form Funktion definiert wird `GetVersionEx` . Die folgenden Werte werden unterstützt:<br /><br /> -VER_PLATFORM_WIN32s oder 0x0000 zum Angeben von Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS oder 0x0001, um Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von Ihnen abgeleitet wurden.<br />-VER_PLATFORM_WIN32_NT oder 0x0002, um Windows NT oder Betriebssysteme anzugeben, die davon abgeleitet wurden.|  
|`dwOSMajorVersion`|Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
|`dwOSMinorVersion`|Die neben Version des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.|  
  
## <a name="remarks"></a>Hinweise  

 `OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen der Microsoft Windows-Plattform-Funktion verwendet wird `GetVersionEx` . Diese Struktur wird von der ASSEMBLYMETADATA-Struktur verwendet, um die Betriebssystemunterstützung anzugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenstrukturen](metadata-structures.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
