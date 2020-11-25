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
ms.openlocfilehash: e3031bf123ff9107b4cebc0723f1be0d423bdaec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721750"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="a94be-102">IApartmentCallback::DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="a94be-102">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="a94be-103">Führt die angegebene Funktion in einem Apartment aus.</span><span class="sxs-lookup"><span data-stu-id="a94be-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a94be-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a94be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a94be-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="a94be-106">in Ein Zeiger auf die Funktion, die im Apartment ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a94be-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="a94be-107">in Ein Zeiger auf das-Argument der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a94be-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94be-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a94be-108">Requirements</span></span>  

 <span data-ttu-id="a94be-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94be-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94be-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a94be-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a94be-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a94be-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a94be-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94be-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94be-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a94be-113">See also</span></span>

- [<span data-ttu-id="a94be-114">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a94be-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
