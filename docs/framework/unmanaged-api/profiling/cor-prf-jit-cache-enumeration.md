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
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500857"
---
# <a name="cor_prf_jit_cache-enumeration"></a>COR_PRF_JIT_CACHE-Enumeration
Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.  
  
> [!NOTE]
> `COR_PRF_CACHED_FUNCTION_FOUND`hat den Wert 0 (null) und `COR_PRF_JIT_CACHE` kann daher nicht als boolesches Ersatz Zeichen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|Bei der Suche wurde die-Funktion gefunden.|  
|`COR_PRF_FUNCTION_NOT_FOUND`|Die Funktion wurde von der Suche nicht gefunden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsenumerationen](profiling-enumerations.md)
