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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796904"
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
 [in, out] Die angeforderte maximale Länge `pwzCachePath`von und bei Rückgabe die tatsächliche Länge von. `pwzCachePath`  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ASM_CACHE_FLAGS-Enumeration](asm-cache-flags-enumeration.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
