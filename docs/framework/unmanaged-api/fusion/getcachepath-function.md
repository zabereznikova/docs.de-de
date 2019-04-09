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
# <a name="getcachepath-function"></a><span data-ttu-id="afa1a-102">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="afa1a-102">GetCachePath Function</span></span>
<span data-ttu-id="afa1a-103">Ruft den Pfad auf der zwischengespeicherte Assembly, die mit den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="afa1a-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa1a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afa1a-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa1a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afa1a-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="afa1a-106">[in] Ein [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Wert, der die Quelle der die zwischengespeicherte Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="afa1a-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="afa1a-107">[out] Der zurückgegebene Zeiger auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="afa1a-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="afa1a-108">[in, out] Die angeforderte maximale Länge des `pwzCachePath`, und bei der Rückgabe die tatsächliche Länge der `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="afa1a-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa1a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="afa1a-109">Requirements</span></span>  
 <span data-ttu-id="afa1a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa1a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa1a-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="afa1a-111">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="afa1a-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="afa1a-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="afa1a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afa1a-113">See also</span></span>

- [<span data-ttu-id="afa1a-114">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="afa1a-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="afa1a-115">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="afa1a-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
