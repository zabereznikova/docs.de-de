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
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150981"
---
# <a name="getcachepath-function"></a>GetCachePath-Funktion
Ruft den Pfad auf der zwischengespeicherte Assembly, die mit den angegebenen Flags.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `dwCacheFlags`  
 [in] Ein [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Wert, der die Quelle der die zwischengespeicherte Assembly angibt.  
  
 `pwzCachePath`  
 [out] Der zurückgegebene Zeiger auf den Pfad.  
  
 `pcchPath`  
 [in, out] Die angeforderte maximale Länge des `pwzCachePath`, und bei der Rückgabe die tatsächliche Länge der `pwzCachePath`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ASM_CACHE_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [Fusion – Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
