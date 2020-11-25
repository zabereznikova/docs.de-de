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
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725628"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="400de-102">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="400de-102">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="400de-103">Stellt Methoden bereit, mit denen der Host die aktuelle Bindungs Richtlinie auswerten und Richtlinien Änderungen für eine angegebene Assembly übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="400de-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="400de-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="400de-104">Methods</span></span>  
  
|<span data-ttu-id="400de-105">Methode</span><span class="sxs-lookup"><span data-stu-id="400de-105">Method</span></span>|<span data-ttu-id="400de-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="400de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="400de-107">EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="400de-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="400de-108">Wertet die Bindungs Richtlinie im Namen des Hosts aus.</span><span class="sxs-lookup"><span data-stu-id="400de-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="400de-109">ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="400de-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="400de-110">Ändert die Bindungs Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="400de-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="400de-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="400de-111">Requirements</span></span>  

 <span data-ttu-id="400de-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="400de-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="400de-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="400de-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="400de-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="400de-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="400de-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="400de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400de-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="400de-116">See also</span></span>

- [<span data-ttu-id="400de-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="400de-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="400de-118">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="400de-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="400de-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="400de-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
