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
ms.openlocfilehash: b5b4210bda7d41b190f1025b62132c5df896a2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703620"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="6d6dd-102">IGCHost::SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="6d6dd-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="6d6dd-103">Legt die maximale Größe des virtuellen Arbeitsspeichers von der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d6dd-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d6dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d6dd-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="6d6dd-106">[in] Die maximale Größe in Megabyte an virtuellem Arbeitsspeicher von der Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d6dd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d6dd-107">Remarks</span></span>  
 <span data-ttu-id="6d6dd-108">Die maximale Größe des virtuellen Arbeitsspeichers von der Runtime kann dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6d6dd-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6dd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d6dd-109">Requirements</span></span>  
 <span data-ttu-id="6d6dd-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6dd-111">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="6d6dd-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6d6dd-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6d6dd-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d6dd-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6dd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d6dd-114">See also</span></span>

- [<span data-ttu-id="6d6dd-115">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d6dd-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
