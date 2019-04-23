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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150981"
---
# <a name="getcachepath-function"></a><span data-ttu-id="0560c-102">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="0560c-102">GetCachePath Function</span></span>
<span data-ttu-id="0560c-103">Ruft den Pfad auf der zwischengespeicherte Assembly, die mit den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="0560c-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0560c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0560c-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0560c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0560c-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="0560c-106">[in] Ein [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Wert, der die Quelle der die zwischengespeicherte Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="0560c-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="0560c-107">[out] Der zurückgegebene Zeiger auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="0560c-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="0560c-108">[in, out] Die angeforderte maximale Länge des `pwzCachePath`, und bei der Rückgabe die tatsächliche Länge der `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="0560c-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0560c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0560c-109">Requirements</span></span>  
 <span data-ttu-id="0560c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0560c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0560c-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0560c-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0560c-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0560c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0560c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0560c-113">See also</span></span>

- [<span data-ttu-id="0560c-114">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0560c-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="0560c-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="0560c-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
