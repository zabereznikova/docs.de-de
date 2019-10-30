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
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128602"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="22205-102">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22205-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="22205-103">Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die Common Language Runtime (CLR) im Falle von Abbrüchen, Timeouts oder Fehlern ausführt.</span><span class="sxs-lookup"><span data-stu-id="22205-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22205-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="22205-104">Methods</span></span>  
  
|<span data-ttu-id="22205-105">Methode</span><span class="sxs-lookup"><span data-stu-id="22205-105">Method</span></span>|<span data-ttu-id="22205-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22205-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22205-107">OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="22205-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="22205-108">Benachrichtigt den Host, dass die CLR die Standardaktion, die durch einen [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) -Befehl angegeben wird, als Reaktion auf einen Thread Abbruch oder <xref:System.AppDomain> entladen übernehmen soll.</span><span class="sxs-lookup"><span data-stu-id="22205-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="22205-109">OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="22205-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="22205-110">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Server Failure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Aufrufe angegebene Aktion in Reaktion auf einen Fehler bei der Ressourcen Zuordnung oder-Wiederherstellung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22205-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="22205-111">OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="22205-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="22205-112">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Abtast Timeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) -Vorgang angegebene Aktion als Antwort auf ein Timeout auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22205-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22205-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22205-113">Requirements</span></span>  
 <span data-ttu-id="22205-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22205-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22205-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="22205-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22205-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="22205-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22205-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22205-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22205-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22205-118">See also</span></span>

- [<span data-ttu-id="22205-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22205-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="22205-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22205-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="22205-121">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22205-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="22205-122">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22205-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="22205-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22205-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
