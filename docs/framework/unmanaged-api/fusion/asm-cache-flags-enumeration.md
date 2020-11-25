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
ms.openlocfilehash: 6c6fab627f21977e85f9885ca4b49a0276faa5ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732163"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Listet den Cache von vorkompilierten Assemblys mithilfe von Ngen.exe auf.|  
|`ASM_CACHE_GAC`|Listet den globalen Assemblycache auf.|  
|`ASM_CACHE_DOWNLOAD`|Listet die Assemblys auf, die bei Bedarf heruntergeladen wurden oder auf die eine Schatten Kopie kopiert wurde.|  
|`ASM_CACHE_ROOT`|Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für die Common Language Runtime (CLR) Version 2,0 zurückgeben soll. Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.|  
|`ASM_CACHE_ROOT_EX`|Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für CLR, Version 4, zurückgeben soll. Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetCachePath-Funktion](getcachepath-function.md)
- [IAssemblyCacheItem-Schnittstelle](iassemblycacheitem-interface.md)
- [Fusionsenumerationen](fusion-enumerations.md)
