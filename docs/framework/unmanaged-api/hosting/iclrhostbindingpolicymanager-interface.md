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
ms.openlocfilehash: e494bbbd08a77329b7b64816216e4bb2e1b724a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984671"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="c3721-102">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3721-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="c3721-103">Stellt Methoden für den Host zum Bewerten von aktuellen Bindungsrichtlinie und kommunizieren von Änderungen für eine angegebene Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="c3721-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3721-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c3721-104">Methods</span></span>  
  
|<span data-ttu-id="c3721-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c3721-105">Method</span></span>|<span data-ttu-id="c3721-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3721-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3721-107">EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="c3721-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="c3721-108">Wertet Richtlinien für die Bindung für den Host.</span><span class="sxs-lookup"><span data-stu-id="c3721-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="c3721-109">ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="c3721-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="c3721-110">Ändert die Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c3721-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3721-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3721-111">Requirements</span></span>  
 <span data-ttu-id="c3721-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3721-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3721-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3721-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3721-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c3721-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3721-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3721-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3721-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3721-116">See also</span></span>

- [<span data-ttu-id="c3721-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3721-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c3721-118">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3721-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="c3721-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c3721-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
