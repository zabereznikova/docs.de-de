---
title: IGCHost::SetVirtualMemLimit-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 9898b760edbb149afcd6bf957a30d0a47287485b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687807"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="cc98c-102">IGCHost::SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="cc98c-102">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="cc98c-103">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="cc98c-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc98c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc98c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc98c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc98c-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="cc98c-106">in Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="cc98c-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc98c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc98c-107">Remarks</span></span>  

 <span data-ttu-id="cc98c-108">Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit kann dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cc98c-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc98c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc98c-109">Requirements</span></span>  

 <span data-ttu-id="cc98c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc98c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc98c-111">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="cc98c-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="cc98c-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cc98c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc98c-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc98c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc98c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc98c-114">See also</span></span>

- [<span data-ttu-id="cc98c-115">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc98c-115">IGCHost Interface</span></span>](igchost-interface.md)
