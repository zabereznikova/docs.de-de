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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140803"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="68126-102">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68126-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="68126-103">Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68126-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68126-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="68126-104">Methods</span></span>  
  
|<span data-ttu-id="68126-105">Methode</span><span class="sxs-lookup"><span data-stu-id="68126-105">Method</span></span>|<span data-ttu-id="68126-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68126-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68126-107">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="68126-108">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="68126-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="68126-109">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="68126-110">Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn für den angegebenen Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="68126-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="68126-111">SetDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="68126-112">Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn der angegebene Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="68126-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="68126-113">SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="68126-114">Legt einen Timeout Wert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="68126-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="68126-115">SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="68126-116">Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die von der CLR bei Auftreten des Vorgangs ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="68126-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="68126-117">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="68126-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="68126-118">Gibt das Verhalten der CLR an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="68126-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68126-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68126-119">Requirements</span></span>  
 <span data-ttu-id="68126-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68126-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68126-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="68126-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68126-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68126-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68126-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68126-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68126-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68126-124">See also</span></span>

- [<span data-ttu-id="68126-125">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="68126-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="68126-126">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="68126-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="68126-127">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="68126-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="68126-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68126-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
