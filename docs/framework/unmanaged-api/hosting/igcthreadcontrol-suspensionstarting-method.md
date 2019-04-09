---
title: IGCThreadControl::SuspensionStarting-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179750"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="edbfe-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="edbfe-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="edbfe-103">Benachrichtigt den Host, dass die Laufzeit eine Threadunterbrechung für eine Garbagecollection oder einer anderen Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="edbfe-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edbfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edbfe-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="edbfe-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edbfe-105">Remarks</span></span>  
 <span data-ttu-id="edbfe-106">Darf nicht verlegt werden alle Threads, während die `SuspensionStarting` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="edbfe-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edbfe-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edbfe-107">Requirements</span></span>  
 <span data-ttu-id="edbfe-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edbfe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edbfe-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="edbfe-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edbfe-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="edbfe-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="edbfe-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="edbfe-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edbfe-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edbfe-112">See also</span></span>

- [<span data-ttu-id="edbfe-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edbfe-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
