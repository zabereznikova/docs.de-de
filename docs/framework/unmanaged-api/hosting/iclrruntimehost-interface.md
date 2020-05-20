---
title: ICLRRuntimeHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: dd1aa4089a981d82ae1403189343694a065a701d
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703663"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="a30f2-102">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a30f2-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="a30f2-103">Bietet ähnliche Funktionen wie die [ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle, die in der .NET Framework Version 1 bereitgestellt wurde, mit den folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="a30f2-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="a30f2-104">Das Hinzufügen der [SetHostControl](iclrruntimehost-sethostcontrol-method.md) -Methode zum Festlegen der Host Steuerelement-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a30f2-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="a30f2-105">Das Weglassen einiger Methoden, die von bereitgestellt werden `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="a30f2-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a30f2-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="a30f2-106">Methods</span></span>  
  
|<span data-ttu-id="a30f2-107">Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-107">Method</span></span>|<span data-ttu-id="a30f2-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a30f2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a30f2-109">ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="a30f2-110">Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a30f2-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="a30f2-111">ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="a30f2-112">Gibt den an, <xref:System.AppDomain> in dem der angegebene verwaltete Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a30f2-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="a30f2-113">ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="a30f2-114">Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly auf.</span><span class="sxs-lookup"><span data-stu-id="a30f2-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="a30f2-115">GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="a30f2-116">Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl](iclrcontrol-interface.md) ab, den Hosts zum Anpassen der Aspekte des Common Language Runtime (CLR) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a30f2-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="a30f2-117">GetCurrentAppDomainId-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="a30f2-118">Ruft den numerischen Bezeichner der ab <xref:System.AppDomain> , die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a30f2-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="a30f2-119">SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="a30f2-120">Legt die Schnittstelle des Host Steuer Elements fest.</span><span class="sxs-lookup"><span data-stu-id="a30f2-120">Sets the host control interface.</span></span> <span data-ttu-id="a30f2-121">Sie müssen aufrufen, `SetHostControl` bevor Sie aufrufen `Start` .</span><span class="sxs-lookup"><span data-stu-id="a30f2-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="a30f2-122">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="a30f2-123">Initialisiert die CLR in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="a30f2-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="a30f2-124">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="a30f2-125">Beendet die Ausführung des Codes durch die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a30f2-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="a30f2-126">UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a30f2-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="a30f2-127">Entlädt das <xref:System.AppDomain> , das dem angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="a30f2-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a30f2-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a30f2-128">Remarks</span></span>  
 <span data-ttu-id="a30f2-129">Beginnen Sie mit der .NET Framework 4, indem Sie die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) -Schnittstelle verwenden, um einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten, und dann die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode aufrufen, um einen Zeiger auf zu erhalten `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="a30f2-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="a30f2-130">In früheren Versionen der .NET Framework erhält der Host einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [corbindtor untimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="a30f2-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="a30f2-131">Zum Bereitstellen von Implementierungen der Technologien, die in der .NET Framework Version 2,0 bereitgestellt werden, müssen Sie `ICLRRuntimeHost` anstelle von verwenden `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="a30f2-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a30f2-132">Rufen Sie die [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) -Methode nicht auf, bevor Sie die [ExecuteApplication](iclrruntimehost-executeapplication-method.md) -Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a30f2-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="a30f2-133">Wenn die- `Start` Methode zuerst aufgerufen wird, kann der `ExecuteApplication` Methodenaufruf nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a30f2-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a30f2-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a30f2-134">Requirements</span></span>  
 <span data-ttu-id="a30f2-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a30f2-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30f2-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a30f2-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a30f2-137">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a30f2-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a30f2-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30f2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30f2-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a30f2-139">See also</span></span>

- [<span data-ttu-id="a30f2-140">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="a30f2-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="a30f2-141">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="a30f2-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="a30f2-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a30f2-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="a30f2-143">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a30f2-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="a30f2-144">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a30f2-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a30f2-145">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="a30f2-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
