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
ms.openlocfilehash: 7092a1c792fee7f6173dcde211b8e807f6ab02a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725585"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="079fe-102">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="079fe-102">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="079fe-103">Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="079fe-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="079fe-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="079fe-104">Methods</span></span>  
  
|<span data-ttu-id="079fe-105">Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-105">Method</span></span>|<span data-ttu-id="079fe-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="079fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="079fe-107">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="079fe-108">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="079fe-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="079fe-109">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="079fe-110">Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn für den angegebenen Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="079fe-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="079fe-111">SetDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="079fe-112">Gibt die Richtlinien Aktion an, die die CLR durchführen soll, wenn der angegebene Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="079fe-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="079fe-113">SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="079fe-114">Legt einen Timeout Wert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="079fe-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="079fe-115">SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="079fe-116">Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die von der CLR bei Auftreten des Vorgangs ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="079fe-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="079fe-117">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="079fe-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="079fe-118">Gibt das Verhalten der CLR an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="079fe-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="079fe-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="079fe-119">Requirements</span></span>  

 <span data-ttu-id="079fe-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="079fe-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="079fe-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="079fe-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="079fe-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="079fe-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="079fe-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="079fe-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="079fe-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="079fe-124">See also</span></span>

- [<span data-ttu-id="079fe-125">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="079fe-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="079fe-126">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="079fe-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="079fe-127">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="079fe-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="079fe-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="079fe-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
