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
ms.openlocfilehash: 9ed317a451e6e35aeac3bc1b83f78d1400ea5c07
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136438"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="beca1-102">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beca1-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="beca1-103">Stellt Methoden bereit, mit denen der Host die aktuelle Bindungs Richtlinie auswerten und Richtlinien Änderungen für eine angegebene Assembly übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="beca1-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="beca1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="beca1-104">Methods</span></span>  
  
|<span data-ttu-id="beca1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="beca1-105">Method</span></span>|<span data-ttu-id="beca1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beca1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="beca1-107">EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="beca1-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="beca1-108">Wertet die Bindungs Richtlinie im Namen des Hosts aus.</span><span class="sxs-lookup"><span data-stu-id="beca1-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="beca1-109">ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="beca1-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="beca1-110">Ändert die Bindungs Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="beca1-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="beca1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="beca1-111">Requirements</span></span>  
 <span data-ttu-id="beca1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beca1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beca1-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="beca1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="beca1-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="beca1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beca1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beca1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beca1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beca1-116">See also</span></span>

- [<span data-ttu-id="beca1-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beca1-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="beca1-118">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beca1-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="beca1-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="beca1-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
