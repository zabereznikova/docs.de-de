---
title: IHostPolicyManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager
helpviewer_keywords: IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f49474f1a75af91ac5296be866914e05732e755
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="85d10-102">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85d10-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="85d10-103">Enthält Methoden, mit die benachrichtigt der Host über die Aktionen, die die common Language Runtime (CLR) im Fall von führt abbricht, Timeouts oder Fehlern.</span><span class="sxs-lookup"><span data-stu-id="85d10-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85d10-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="85d10-104">Methods</span></span>  
  
|<span data-ttu-id="85d10-105">Methode</span><span class="sxs-lookup"><span data-stu-id="85d10-105">Method</span></span>|<span data-ttu-id="85d10-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85d10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85d10-107">OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="85d10-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="85d10-108">Benachrichtigt den Host, dass die CLR die Standardaktion angegeben, die durch einen Aufruf von [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) als Antwort auf einen Thread abzubrechen oder <xref:System.AppDomain> entladen.</span><span class="sxs-lookup"><span data-stu-id="85d10-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="85d10-109">OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="85d10-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="85d10-110">Benachrichtigt den Host, dass die CLR die Aktion angegeben, die durch einen Aufruf von [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) als Antwort auf einen Fehler bei der Reservierung oder Freigabe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="85d10-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="85d10-111">OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="85d10-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="85d10-112">Benachrichtigt den Host, dass die CLR die Aktion angegeben, die durch einen Aufruf von [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) Reaktion auf ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="85d10-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85d10-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85d10-113">Requirements</span></span>  
 <span data-ttu-id="85d10-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85d10-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d10-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85d10-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85d10-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85d10-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85d10-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d10-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d10-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85d10-118">See Also</span></span>  
 [<span data-ttu-id="85d10-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="85d10-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="85d10-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="85d10-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="85d10-121">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="85d10-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="85d10-122">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85d10-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="85d10-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85d10-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
