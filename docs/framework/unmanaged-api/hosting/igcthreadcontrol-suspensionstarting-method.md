---
title: IGCThreadControl::SuspensionStarting-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d5f403c2880d0079a89c6de5c2ad9aa4f8d9fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="ebc60-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="ebc60-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="ebc60-103">Benachrichtigt den Host, dass die Common Language Runtime einen Thread anhalten für eine Garbagecollection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="ebc60-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebc60-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ebc60-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebc60-105">Remarks</span></span>  
 <span data-ttu-id="ebc60-106">Darf nicht verlegt werden alle Threads, die während der `SuspensionStarting` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="ebc60-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc60-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ebc60-107">Requirements</span></span>  
 <span data-ttu-id="ebc60-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc60-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc60-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebc60-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebc60-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ebc60-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebc60-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc60-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc60-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc60-112">See Also</span></span>  
 [<span data-ttu-id="ebc60-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebc60-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
