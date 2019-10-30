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
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138230"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="a8229-102">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8229-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="a8229-103">Beschreibt die Richtlinien Aktionen, die der Host für Vorgänge festlegen kann, die durch [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) und Fehler beschrieben werden, die von [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a8229-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8229-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8229-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="a8229-105">Member</span><span class="sxs-lookup"><span data-stu-id="a8229-105">Members</span></span>  
  
|<span data-ttu-id="a8229-106">Member</span><span class="sxs-lookup"><span data-stu-id="a8229-106">Member</span></span>|<span data-ttu-id="a8229-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8229-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="a8229-108">Gibt an, dass die Common Language Runtime (CLR) den Thread ordnungsgemäß abbrechen soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="a8229-109">Ein ordnungsgemäßer Abbruch umfasst den Versuch, alle `finally` Blöcke, alle `catch` Blöcke im Zusammenhang mit Thread Abbrüchen und Finalizern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8229-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="a8229-110">Gibt an, dass die CLR einen deaktivierten Zustand aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="a8229-111">Im betroffenen Prozess kann kein weiterer verwalteter Code ausgeführt werden, und Threads können nicht in die CLR-Datei eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a8229-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="a8229-112">Gibt an, dass die CLR eine ordnungsgemäße Beendigung des Prozesses versuchen soll, einschließlich der Ausführung von Finalizern und der Ausführung von Bereinigung-und Protokollierungs Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="a8229-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="a8229-113">Gibt an, dass die CLR den Prozess sofort beenden soll, ohne Finalizer auszuführen oder Bereinigungs-und Protokollierungs Vorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8229-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="a8229-114">Die Benachrichtigung wird jedoch an den Debugger gesendet.</span><span class="sxs-lookup"><span data-stu-id="a8229-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="a8229-115">Gibt an, dass keine Aktion ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="a8229-116">Gibt an, dass die CLR einen unhöflichen Thread Abbruch ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="a8229-117">Nur die `catch` und `finally` Blöcke, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8229-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="a8229-118">Gibt an, dass die CLR den Prozess beenden soll, ohne Finalizer oder Protokollierungs Vorgänge ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a8229-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="a8229-119">Gibt an, dass die CLR eine unhöfliche Entladung des <xref:System.AppDomain>ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="a8229-120">Nur Finalizer, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8229-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="a8229-121">Ebenso erhalten alle Threads mit diesem <xref:System.AppDomain> in Ihrem Stapel eine `ThreadAbortException`, aber nur die `catch` und `finally` Blöcke, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8229-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="a8229-122">Gibt an, dass eine für die Bedingung geeignete Ausnahme, z. b. nicht genügend Arbeitsspeicher, Pufferüberlauf usw., ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="a8229-123">Gibt an, dass die <xref:System.AppDomain> entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8229-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="a8229-124">Die CLR versucht, Finalizer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8229-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8229-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8229-125">Remarks</span></span>  
 <span data-ttu-id="a8229-126">Der Host legt Richtlinien Aktionen durch Aufrufen von Methoden der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) -Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="a8229-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="a8229-127">Informationen über grobe und ordnungsgemäße Abbrüche finden Sie in der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a8229-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8229-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8229-128">Requirements</span></span>  
 <span data-ttu-id="a8229-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8229-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8229-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a8229-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8229-131">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a8229-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8229-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8229-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8229-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8229-133">See also</span></span>

- [<span data-ttu-id="a8229-134">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8229-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a8229-135">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8229-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="a8229-136">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8229-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="a8229-137">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a8229-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
