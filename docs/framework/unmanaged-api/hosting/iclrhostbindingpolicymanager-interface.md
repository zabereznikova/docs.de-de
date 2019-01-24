---
title: ICLRHostBindingPolicyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98a2978b440e0e72b3b4c1ac3065fbaf5d70e508
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666097"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="24254-102">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24254-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="24254-103">Stellt Methoden für den Host zum Bewerten von aktuellen Bindungsrichtlinie und kommunizieren von Änderungen für eine angegebene Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="24254-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24254-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="24254-104">Methods</span></span>  
  
|<span data-ttu-id="24254-105">Methode</span><span class="sxs-lookup"><span data-stu-id="24254-105">Method</span></span>|<span data-ttu-id="24254-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24254-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24254-107">EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="24254-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="24254-108">Wertet Richtlinien für die Bindung für den Host.</span><span class="sxs-lookup"><span data-stu-id="24254-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="24254-109">ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="24254-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="24254-110">Ändert die Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="24254-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24254-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24254-111">Requirements</span></span>  
 <span data-ttu-id="24254-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24254-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24254-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24254-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24254-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24254-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24254-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24254-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24254-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24254-116">See also</span></span>
- [<span data-ttu-id="24254-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24254-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="24254-118">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24254-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="24254-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="24254-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
