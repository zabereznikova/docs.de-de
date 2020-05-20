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
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703568"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="be8c6-102">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be8c6-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="be8c6-103">Stellt Methoden bereit, mit denen der Host die aktuelle Bindungs Richtlinie auswerten und Richtlinien Änderungen für eine angegebene Assembly übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="be8c6-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be8c6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="be8c6-104">Methods</span></span>  
  
|<span data-ttu-id="be8c6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="be8c6-105">Method</span></span>|<span data-ttu-id="be8c6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="be8c6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be8c6-107">EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="be8c6-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="be8c6-108">Wertet die Bindungs Richtlinie im Namen des Hosts aus.</span><span class="sxs-lookup"><span data-stu-id="be8c6-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="be8c6-109">ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="be8c6-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="be8c6-110">Ändert die Bindungs Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="be8c6-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be8c6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be8c6-111">Requirements</span></span>  
 <span data-ttu-id="be8c6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be8c6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be8c6-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="be8c6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be8c6-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="be8c6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be8c6-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be8c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8c6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be8c6-116">See also</span></span>

- [<span data-ttu-id="be8c6-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be8c6-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="be8c6-118">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be8c6-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="be8c6-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="be8c6-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
