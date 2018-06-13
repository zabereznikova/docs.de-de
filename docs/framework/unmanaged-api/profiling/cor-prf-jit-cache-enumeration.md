---
title: COR_PRF_JIT_CACHE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8c972bcace3ba3d855a3b5eebc16e6b76994eb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450703"
---
# <a name="corprfjitcache-enumeration"></a>COR_PRF_JIT_CACHE-Enumeration
Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` hat den Wert 0 (null), sodass `COR_PRF_JIT_CACHE` kann nicht als boolescher Ersatzzeichen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|Die Suche wurde die Funktion gefunden.|  
|`COR_PRF_FUNCTION_NOT_FOUND`|Die Suche hat die Funktion nicht gefunden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
