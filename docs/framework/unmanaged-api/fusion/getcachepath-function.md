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
# <a name="getcachepath-function"></a><span data-ttu-id="34cce-102">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="34cce-102">GetCachePath Function</span></span>
<span data-ttu-id="34cce-103">Ruft den Pfad zur zwischengespeicherten Assembly unter Verwendung der angegebenen Flags ab.</span><span class="sxs-lookup"><span data-stu-id="34cce-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34cce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34cce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="34cce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34cce-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="34cce-106">in Ein [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) -Wert, der die Quelle der zwischengespeicherten Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="34cce-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="34cce-107">vorgenommen Der zurückgegebene Zeiger auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="34cce-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="34cce-108">[in, out] Die angeforderte maximale Länge `pwzCachePath`von und bei Rückgabe die tatsächliche Länge von. `pwzCachePath`</span><span class="sxs-lookup"><span data-stu-id="34cce-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34cce-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34cce-109">Requirements</span></span>  
 <span data-ttu-id="34cce-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34cce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34cce-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="34cce-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="34cce-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34cce-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34cce-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34cce-113">See also</span></span>

- [<span data-ttu-id="34cce-114">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="34cce-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="34cce-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="34cce-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
