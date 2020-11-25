---
title: RUNTIME_INFO_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 6f4fbb40053628d60ba7f094fcb5d50a94d63e1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729940"
---
# <a name="runtime_info_flags-enumeration"></a>RUNTIME_INFO_FLAGS-Enumeration

Enthält Werte, die angeben, welche Informationen zum Common Language Runtime (CLR) zurückgegeben werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Gibt an, dass Verzeichnisinformationen nicht eingeschlossen werden sollen.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Gibt an, dass keine Versionsinformationen eingeschlossen werden sollen.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Gibt an, dass ein Fehler Dialogfeld bei einem Fehler nicht angezeigt werden soll.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Gibt an, dass die Auswirkungen des Aufrufs der [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) -Funktion mit dem SEM_FAILCRITICALERRORS-Flag überschrieben werden sollen. Das heißt, ein Installations Dialogfeld sollte bei einem Fehler angezeigt werden, anstatt unterdrückt zu werden.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Gibt eine Anforderung von Informationen über eine mit AMD 64 kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_REQUEST_IA64`|Gibt eine Anforderung von Informationen über eine IA-64-kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_REQUEST_X86`|Gibt eine Anforderung von Informationen über eine x86-kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Gibt an, dass Informationen zur Versions Aktualisierung eingeschlossen werden sollen.|  
  
## <a name="remarks"></a>Hinweise  

 Die folgenden Plattformarchitektur-Flags können jeweils nur einzeln angegeben werden und können nicht kombiniert werden:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
