---
title: ASM_CACHE_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27caa9916b5adab2b2049a8f66ac34fed40e4d7f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778575"
---
# <a name="asmcacheflags-enumeration"></a>ASM_CACHE_FLAGS-Enumeration
Gibt die Quelle einer Assembly, die durch dargestellt [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) im globalen Assemblycache.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Listet den Cache der vorkompilierten Assemblys mit Ngen.exe an.|  
|`ASM_CACHE_GAC`|Listet die im globalen Assemblycache.|  
|`ASM_CACHE_DOWNLOAD`|Listet die Assemblys, die bei Bedarf heruntergeladen wurden, oder, die verborgen kopiert wurde.|  
|`ASM_CACHE_ROOT`|Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zurückgeben, im globalen Assemblycache für die common Language Runtime (CLR) Version 2.0. Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zum globalen Assemblycache zurückgeben, für die CLR, Version 4. Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetCachePath-Funktion](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [IAssemblyCacheItem-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [Fusion-Enumerationen](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
