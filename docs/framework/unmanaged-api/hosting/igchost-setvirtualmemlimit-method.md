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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1d61c8aeaf458d8cbbd2976fa83aaa0eeb0f834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437738"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="71278-102">IGCHost::SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="71278-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="71278-103">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="71278-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71278-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71278-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71278-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71278-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="71278-106">[in] Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="71278-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71278-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71278-107">Remarks</span></span>  
 <span data-ttu-id="71278-108">Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit kann dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="71278-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71278-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71278-109">Requirements</span></span>  
 <span data-ttu-id="71278-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71278-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71278-111">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="71278-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="71278-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71278-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71278-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71278-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71278-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71278-114">See Also</span></span>  
 [<span data-ttu-id="71278-115">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71278-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
