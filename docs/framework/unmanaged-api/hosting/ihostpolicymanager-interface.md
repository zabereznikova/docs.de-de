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
ms.openlocfilehash: db089a55128fa675ceedf157b046fe205d8c6b51
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804329"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="d2111-102">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2111-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="d2111-103">Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die Common Language Runtime (CLR) im Falle von Abbrüchen, Timeouts oder Fehlern ausführt.</span><span class="sxs-lookup"><span data-stu-id="d2111-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2111-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d2111-104">Methods</span></span>  
  
|<span data-ttu-id="d2111-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d2111-105">Method</span></span>|<span data-ttu-id="d2111-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2111-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2111-107">OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="d2111-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="d2111-108">Benachrichtigt den Host, dass die CLR im Begriff ist, die Standardaktion zu übernehmen, die durch einen [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) -Vorgang als Reaktion auf einen Thread Abbruch oder entladen angegeben wird <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d2111-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="d2111-109">OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="d2111-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="d2111-110">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Server Failure](iclrpolicymanager-setactiononfailure-method.md) -Aufrufe angegebene Aktion in Reaktion auf einen Fehler bei der Ressourcen Zuordnung oder-Wiederherstellung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d2111-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="d2111-111">OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="d2111-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="d2111-112">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Abtast Timeout](iclrpolicymanager-setactionontimeout-method.md) -Vorgang angegebene Aktion als Antwort auf ein Timeout auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d2111-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2111-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2111-113">Requirements</span></span>  
 <span data-ttu-id="d2111-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2111-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2111-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d2111-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2111-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2111-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2111-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2111-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2111-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2111-118">See also</span></span>

- [<span data-ttu-id="d2111-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2111-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="d2111-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2111-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d2111-121">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2111-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="d2111-122">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2111-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="d2111-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2111-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
