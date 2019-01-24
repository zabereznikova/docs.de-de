---
title: EPolicyAction-Enumeration
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80a0e8d37e834ea0a7623517e2e1228a79d9ea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655711"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="ecb8b-102">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ecb8b-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="ecb8b-103">Beschreibt die Richtlinienaktionen, der Host kann für Vorgänge, die durch beschrieben festlegen [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) sowie durch beschriebene Fehler [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ecb8b-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecb8b-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="ecb8b-105">Member</span><span class="sxs-lookup"><span data-stu-id="ecb8b-105">Members</span></span>  
  
|<span data-ttu-id="ecb8b-106">Member</span><span class="sxs-lookup"><span data-stu-id="ecb8b-106">Member</span></span>|<span data-ttu-id="ecb8b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecb8b-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="ecb8b-108">Gibt an, dass die common Language Runtime (CLR) den Thread ordnungsgemäß abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="ecb8b-109">Ein ordnungsgemäßer Abbruch beinhaltet versuchen der Ausführung alle `finally` Blöcke, alle `catch` Blöcke im Zusammenhang mit der Threadabbrüche und Finalizer.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="ecb8b-110">Gibt an, dass die CLR deaktiviert eingeben soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="ecb8b-111">Verwalteter Code kann keine weiteren des betroffenen Prozesses ausgeführt werden, und der CLR Threads blockiert.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="ecb8b-112">Gibt an, dass die CLR dem ordnungsgemäßen Beenden der Prozess, einschließlich der Ausführung von Finalizern und Bereinigung und protokollieren soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="ecb8b-113">Gibt an, dass die CLR den Prozess sofort beendet werden soll ohne Ausführung von Finalizern oder Bereinigung und Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="ecb8b-114">Jedoch ein wird die Benachrichtigung an den Debugger gesendet.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-114">Nowever, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="ecb8b-115">Gibt an, dass keine Aktion ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="ecb8b-116">Gibt an, dass die CLR einen grobe Threadabbruch ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="ecb8b-117">Nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="ecb8b-118">Gibt an, dass die CLR den Prozess beendet werden soll, ohne Ausführung von Finalizern oder Vorgänge protokollieren.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="ecb8b-119">Gibt an, dass die CLR ein grobe Entladen durchführen, sollten die <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="ecb8b-120">Nur Finalizer mit markierten <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="ecb8b-121">Auf ähnliche Weise alle Threads mit dieser <xref:System.AppDomain> in ihrem Stapel erhalten eine `ThreadAbortException`, sondern nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="ecb8b-122">Gibt an, dass es sich bei der Bedingung, z. B. Out-of-Memory, Pufferüberlauf usw., entsprechende Ausnahme ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="ecb8b-123">Gibt an, dass die <xref:System.AppDomain> entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="ecb8b-124">Die CLR versucht, die Finalizer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecb8b-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecb8b-125">Remarks</span></span>  
 <span data-ttu-id="ecb8b-126">Der Host setzt Richtlinienaktionen durch Aufrufen der Methoden der der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="ecb8b-127">Informationen über grobe und ordnungsgemäße Abbrüche finden Sie unter den [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ecb8b-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb8b-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecb8b-128">Requirements</span></span>  
 <span data-ttu-id="ecb8b-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecb8b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb8b-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ecb8b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecb8b-131">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecb8b-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecb8b-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb8b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb8b-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecb8b-133">See also</span></span>
- [<span data-ttu-id="ecb8b-134">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ecb8b-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="ecb8b-135">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecb8b-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="ecb8b-136">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecb8b-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="ecb8b-137">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ecb8b-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
