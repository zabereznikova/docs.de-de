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
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723154"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="2bc11-102">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="2bc11-102">_CorImageUnloading Function</span></span>

<span data-ttu-id="2bc11-103">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="2bc11-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="2bc11-104">Diese Funktion ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="2bc11-104">This function is not implemented.</span></span> <span data-ttu-id="2bc11-105">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2bc11-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc11-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bc11-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc11-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bc11-107">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="2bc11-108">in Ein Zeiger auf die Startposition des zu entladenden Bilds.</span><span class="sxs-lookup"><span data-stu-id="2bc11-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc11-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2bc11-109">Requirements</span></span>  

 <span data-ttu-id="2bc11-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bc11-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc11-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2bc11-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bc11-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2bc11-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bc11-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc11-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc11-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bc11-114">See also</span></span>

- [<span data-ttu-id="2bc11-115">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="2bc11-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
