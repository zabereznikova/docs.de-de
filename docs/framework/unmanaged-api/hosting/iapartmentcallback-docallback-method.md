---
title: IApartmentCallback::DoCallback-Methode
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 9bb257a3d84d5022b9ae13c89a34572485d3033b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126947"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="6c038-102">IApartmentCallback::DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="6c038-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="6c038-103">Führt die angegebene Funktion in einem Apartment aus.</span><span class="sxs-lookup"><span data-stu-id="6c038-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c038-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c038-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c038-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c038-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="6c038-106">in Ein Zeiger auf die Funktion, die im Apartment ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c038-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="6c038-107">in Ein Zeiger auf das-Argument der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6c038-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c038-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c038-108">Requirements</span></span>  
 <span data-ttu-id="6c038-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c038-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c038-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6c038-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c038-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c038-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c038-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c038-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c038-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c038-113">See also</span></span>

- [<span data-ttu-id="6c038-114">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c038-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
