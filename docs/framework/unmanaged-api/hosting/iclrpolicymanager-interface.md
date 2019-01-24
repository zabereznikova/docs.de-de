---
title: ICLRPolicyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfce4276c651e5cb6ed20bd2616b68294e49da8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629144"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="00c76-102">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00c76-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="00c76-103">Enthält Methoden, die den Host Geben Sie die, die bei Fehlern oder Timeouts auszuführenden Richtlinienaktionen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="00c76-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00c76-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="00c76-104">Methods</span></span>  
  
|<span data-ttu-id="00c76-105">Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-105">Method</span></span>|<span data-ttu-id="00c76-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00c76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00c76-107">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="00c76-108">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="00c76-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="00c76-109">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="00c76-110">Gibt die Richtlinienaktion, die die CLR ausführen soll, wenn der angegebene Vorgang ein auftritt Timeout.</span><span class="sxs-lookup"><span data-stu-id="00c76-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="00c76-111">SetDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="00c76-112">Gibt die Richtlinienaktion, die die CLR ausführen soll, wenn der angegebene Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="00c76-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="00c76-113">SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="00c76-114">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="00c76-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="00c76-115">SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="00c76-116">Legt einen Timeoutwert für den angegebenen Vorgang und gibt die Richtlinienaktion, die die CLR ausführen soll, wenn der Vorgang erfolgt.</span><span class="sxs-lookup"><span data-stu-id="00c76-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="00c76-117">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="00c76-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="00c76-118">Gibt das Verhalten der CLR an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="00c76-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00c76-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00c76-119">Requirements</span></span>  
 <span data-ttu-id="00c76-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00c76-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c76-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00c76-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00c76-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="00c76-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00c76-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00c76-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c76-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00c76-124">See also</span></span>
- [<span data-ttu-id="00c76-125">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="00c76-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="00c76-126">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="00c76-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="00c76-127">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="00c76-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="00c76-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00c76-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
