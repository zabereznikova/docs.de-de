---
title: _CorImageUnloading-Funktion
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebd7ef3b329eae8e35b680f3d8c74864e2a0f4d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428686"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="f2d0a-102">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="f2d0a-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="f2d0a-103">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="f2d0a-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="f2d0a-104">Diese Funktion ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f2d0a-104">This function is not implemented.</span></span> <span data-ttu-id="f2d0a-105">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2d0a-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d0a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2d0a-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2d0a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2d0a-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f2d0a-108">[in] Ein Zeiger auf die Anfangsposition des Abbilds, das entladen.</span><span class="sxs-lookup"><span data-stu-id="f2d0a-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d0a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2d0a-109">Requirements</span></span>  
 <span data-ttu-id="f2d0a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2d0a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2d0a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2d0a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2d0a-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2d0a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2d0a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2d0a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d0a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d0a-114">See Also</span></span>  
 [<span data-ttu-id="f2d0a-115">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="f2d0a-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
