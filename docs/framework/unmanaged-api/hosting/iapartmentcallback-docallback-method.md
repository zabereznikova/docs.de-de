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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77a2ccaf6f972fadd8396378dc7777ec4c85120d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970052"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="2ed44-102">IApartmentCallback::DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="2ed44-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="2ed44-103">Führt die angegebene Funktion innerhalb eines Apartments an.</span><span class="sxs-lookup"><span data-stu-id="2ed44-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ed44-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ed44-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="2ed44-106">[in] Ein Zeiger auf die Funktion, die in dem Apartment ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ed44-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="2ed44-107">[in] Ein Zeiger auf das Argument der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ed44-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed44-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ed44-108">Requirements</span></span>  
 <span data-ttu-id="2ed44-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ed44-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed44-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ed44-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ed44-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2ed44-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ed44-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed44-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed44-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ed44-113">See also</span></span>

- [<span data-ttu-id="2ed44-114">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ed44-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
