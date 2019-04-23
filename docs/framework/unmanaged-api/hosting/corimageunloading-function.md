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
ms.openlocfilehash: 1cb5f9decbcdfb71f67a5132dc59773f1de8b0a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086428"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="15493-102">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="15493-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="15493-103">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="15493-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="15493-104">Diese Funktion ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="15493-104">This function is not implemented.</span></span> <span data-ttu-id="15493-105">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="15493-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15493-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="15493-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15493-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="15493-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="15493-108">[in] Ein Zeiger auf den Anfangsort des Bildes, das nicht entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="15493-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15493-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15493-109">Requirements</span></span>  
 <span data-ttu-id="15493-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15493-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15493-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15493-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15493-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15493-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15493-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15493-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15493-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15493-114">See also</span></span>

- [<span data-ttu-id="15493-115">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="15493-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
