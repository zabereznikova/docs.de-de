---
title: IHostPolicyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760115"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="95477-102">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95477-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="95477-103">Enthält Methoden, die abgebrochen wird der Host über die Aktionen, die die common Language Runtime (CLR) im Fall von ausführt, Timeouts oder Fehlern zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="95477-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95477-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="95477-104">Methods</span></span>  
  
|<span data-ttu-id="95477-105">Methode</span><span class="sxs-lookup"><span data-stu-id="95477-105">Method</span></span>|<span data-ttu-id="95477-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95477-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95477-107">OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="95477-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="95477-108">Benachrichtigt den Host, der die CLR die Standardaktion angegeben, die durch einen Aufruf von [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) als Reaktion auf einen Thread abgebrochen oder <xref:System.AppDomain> nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="95477-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="95477-109">OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="95477-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="95477-110">Benachrichtigt den Host, die die CLR wird durch einen Aufruf von angegebene Aktion ausführen [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) als Reaktion auf einen Fehler bei der Belegung oder Freigabe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="95477-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="95477-111">OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="95477-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="95477-112">Benachrichtigt den Host, die die CLR wird durch einen Aufruf von angegebene Aktion ausführen [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) als Reaktion auf ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="95477-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95477-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95477-113">Requirements</span></span>  
 <span data-ttu-id="95477-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95477-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95477-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95477-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95477-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="95477-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95477-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95477-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95477-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95477-118">See also</span></span>

- [<span data-ttu-id="95477-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95477-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="95477-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95477-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="95477-121">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95477-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="95477-122">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95477-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="95477-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="95477-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
