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
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795278"
---
# <a name="asm_cache_flags-enumeration"></a>ASM_CACHE_FLAGS-Enumeration
Gibt die Quelle einer Assembly an, die von [IAssemblyCacheItem im globalen Assemblycache](iassemblycacheitem-interface.md) dargestellt wird.  
  
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
|`ASM_CACHE_ZAP`|Listet den Cache von vorkompilierten Assemblys mithilfe von "ngen. exe" auf.|  
|`ASM_CACHE_GAC`|Listet den globalen Assemblycache auf.|  
|`ASM_CACHE_DOWNLOAD`|Listet die Assemblys auf, die bei Bedarf heruntergeladen wurden oder auf die eine Schatten Kopie kopiert wurde.|  
|`ASM_CACHE_ROOT`|Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für die Common Language Runtime (CLR) Version 2,0 zurückgeben soll. Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.|  
|`ASM_CACHE_ROOT_EX`|Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für CLR, Version 4, zurückgeben soll. Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetCachePath-Funktion](getcachepath-function.md)
- [IAssemblyCacheItem-Schnittstelle](iassemblycacheitem-interface.md)
- [Fusion-Enumerationen](fusion-enumerations.md)
