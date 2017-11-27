---
title: GetCachePath-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: GetCachePath
helpviewer_keywords: GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 924482bf34d53d3d7144c4bae93a00a8f8d2ad4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getcachepath-function"></a>GetCachePath-Funktion
Ruft den Pfad der zwischengespeicherten Assembly mithilfe der angegebenen Flags.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwCacheFlags`  
 [in] Ein [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Wert, der die Quelle der zwischengespeicherten Assembly angibt.  
  
 `pwzCachePath`  
 [out] Der zurückgegebene Zeiger auf den Pfad.  
  
 `pcchPath`  
 [in, out] Die angeforderte maximale Länge des `pwzCachePath`, und bei Rückgabe, die tatsächliche Länge der `pwzCachePath`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ASM_CACHE_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [Globale statische Fusionsfunktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
