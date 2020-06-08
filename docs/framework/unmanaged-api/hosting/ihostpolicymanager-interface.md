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
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503938"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="8f736-102">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f736-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="8f736-103">Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die Common Language Runtime (CLR) im Falle von Abbrüchen, Timeouts oder Fehlern ausführt.</span><span class="sxs-lookup"><span data-stu-id="8f736-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f736-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8f736-104">Methods</span></span>  
  
|<span data-ttu-id="8f736-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8f736-105">Method</span></span>|<span data-ttu-id="8f736-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f736-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f736-107">OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="8f736-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="8f736-108">Benachrichtigt den Host, dass die CLR im Begriff ist, die Standardaktion zu übernehmen, die durch einen [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) -Vorgang als Reaktion auf einen Thread Abbruch oder entladen angegeben wird <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="8f736-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="8f736-109">OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="8f736-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="8f736-110">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Server Failure](iclrpolicymanager-setactiononfailure-method.md) -Aufrufe angegebene Aktion in Reaktion auf einen Fehler bei der Ressourcen Zuordnung oder-Wiederherstellung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8f736-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="8f736-111">OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="8f736-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="8f736-112">Benachrichtigt den Host, dass die CLR im Begriff ist, die durch einen [ICLRPolicyManager:: Abtast Timeout](iclrpolicymanager-setactionontimeout-method.md) -Vorgang angegebene Aktion als Antwort auf ein Timeout auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8f736-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f736-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8f736-113">Requirements</span></span>  
 <span data-ttu-id="8f736-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f736-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f736-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8f736-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f736-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f736-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f736-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f736-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f736-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8f736-118">See also</span></span>

- [<span data-ttu-id="8f736-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f736-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="8f736-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f736-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="8f736-121">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f736-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="8f736-122">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f736-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="8f736-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8f736-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
