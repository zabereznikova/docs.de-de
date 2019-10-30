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
# <a name="getcachepath-function"></a><span data-ttu-id="9205e-102">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="9205e-102">GetCachePath Function</span></span>
<span data-ttu-id="9205e-103">Ruft den Pfad zur zwischengespeicherten Assembly unter Verwendung der angegebenen Flags ab.</span><span class="sxs-lookup"><span data-stu-id="9205e-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9205e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9205e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9205e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9205e-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="9205e-106">in Ein [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) -Wert, der die Quelle der zwischengespeicherten Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="9205e-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="9205e-107">vorgenommen Der zurückgegebene Zeiger auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="9205e-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="9205e-108">[in, out] Die angeforderte maximale Länge `pwzCachePath`und bei Rückgabe der tatsächlichen Länge `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="9205e-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9205e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9205e-109">Requirements</span></span>  
 <span data-ttu-id="9205e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9205e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9205e-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9205e-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9205e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9205e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9205e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9205e-113">See also</span></span>

- [<span data-ttu-id="9205e-114">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9205e-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="9205e-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="9205e-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
