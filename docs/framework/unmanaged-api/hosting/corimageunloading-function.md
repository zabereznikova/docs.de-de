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
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616537"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="e3efb-102">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="e3efb-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="e3efb-103">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="e3efb-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="e3efb-104">Diese Funktion ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="e3efb-104">This function is not implemented.</span></span> <span data-ttu-id="e3efb-105">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3efb-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3efb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3efb-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3efb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3efb-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="e3efb-108">in Ein Zeiger auf die Startposition des zu entladenden Bilds.</span><span class="sxs-lookup"><span data-stu-id="e3efb-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3efb-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3efb-109">Requirements</span></span>  
 <span data-ttu-id="e3efb-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3efb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3efb-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e3efb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3efb-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e3efb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3efb-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3efb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3efb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3efb-114">See also</span></span>

- [<span data-ttu-id="e3efb-115">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="e3efb-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
