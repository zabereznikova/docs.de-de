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
ms.openlocfilehash: c060e4883335a8318970b5fbd74bf72c9e13f5bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134859"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="fdc5b-102">IGCHost::SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="fdc5b-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="fdc5b-103">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="fdc5b-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdc5b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdc5b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdc5b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="fdc5b-106">in Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="fdc5b-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdc5b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdc5b-107">Remarks</span></span>  
 <span data-ttu-id="fdc5b-108">Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit kann dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fdc5b-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc5b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdc5b-109">Requirements</span></span>  
 <span data-ttu-id="fdc5b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdc5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc5b-111">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="fdc5b-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fdc5b-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fdc5b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdc5b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc5b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdc5b-114">See also</span></span>

- [<span data-ttu-id="fdc5b-115">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdc5b-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
