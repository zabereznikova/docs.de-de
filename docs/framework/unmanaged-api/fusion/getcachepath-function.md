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
ms.openlocfilehash: c22f0701cfda4523f595366a97435ef8da08b0cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724467"
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
 in Ein [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) Wert, der die Quelle der zwischengespeicherten Assembly angibt.  
  
 `pwzCachePath`  
 vorgenommen Der zurückgegebene Zeiger auf den Pfad.  
  
 `pcchPath`  
 [in, out] Die angeforderte maximale Länge von `pwzCachePath` und bei Rückgabe die tatsächliche Länge von `pwzCachePath` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ASM_CACHE_FLAGS-Enumeration](asm-cache-flags-enumeration.md)
- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
