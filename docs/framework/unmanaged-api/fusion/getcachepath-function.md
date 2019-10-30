---
title: GetCachePath-Funktion
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132700"
---
# <a name="getcachepath-function"></a>GetCachePath-Funktion
Ruft den Pfad zur zwischengespeicherten Assembly unter Verwendung der angegebenen Flags ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `dwCacheFlags`  
 in Ein [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) -Wert, der die Quelle der zwischengespeicherten Assembly angibt.  
  
 `pwzCachePath`  
 vorgenommen Der zurückgegebene Zeiger auf den Pfad.  
  
 `pcchPath`  
 [in, out] Die angeforderte maximale Länge `pwzCachePath`und bei Rückgabe der tatsächlichen Länge `pwzCachePath`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ASM_CACHE_FLAGS-Enumeration](asm-cache-flags-enumeration.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
