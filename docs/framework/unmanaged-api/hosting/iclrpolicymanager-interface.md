---
title: ICLRPolicyManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3dd904184b730a5b0f5b2dfcac4197e708544d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="7f497-102">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f497-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="7f497-103">Enthält Methoden, mit die den Host Geben Sie die für Richtlinienaktionen, die im Falle von Fehlern und Timeouts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="7f497-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f497-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7f497-104">Methods</span></span>  
  
|<span data-ttu-id="7f497-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-105">Method</span></span>|<span data-ttu-id="7f497-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f497-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f497-107">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="7f497-108">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausführen sollten, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f497-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="7f497-109">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="7f497-110">Gibt die Richtlinienaktion, die die CLR ausführen sollten, wenn der angegebene Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f497-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="7f497-111">SetDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="7f497-112">Gibt die Richtlinienaktion, die die CLR ausführen sollten, wenn der angegebene Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f497-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="7f497-113">SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="7f497-114">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="7f497-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="7f497-115">SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="7f497-116">Legt einen Timeoutwert für den angegebenen Vorgang und gibt die Richtlinienaktion, die die CLR ausführen sollten, wenn der Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f497-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="7f497-117">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="7f497-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="7f497-118">Gibt das Verhalten der CLR, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f497-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f497-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f497-119">Requirements</span></span>  
 <span data-ttu-id="7f497-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f497-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f497-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7f497-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f497-122">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7f497-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f497-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f497-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f497-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f497-124">See Also</span></span>  
 [<span data-ttu-id="7f497-125">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7f497-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="7f497-126">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7f497-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="7f497-127">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7f497-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="7f497-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f497-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
