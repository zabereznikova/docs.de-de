---
title: ICLRRuntimeHost-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost
helpviewer_keywords: ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type: apiref
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 332db2680ca23f34893a6c50c5311d73838bc1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="82a47-102">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82a47-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="82a47-103">Bietet Funktionen, die ähnlich dem Konzept der [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) Schnittstelle bereitgestellt, die in .NET Framework, Version 1, mit den folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="82a47-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="82a47-104">Das Hinzufügen der [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) Methode zum Festlegen der Schnittstelle des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="82a47-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="82a47-105">Die Auslassung einiger Methoden gebotenen `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="82a47-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82a47-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="82a47-106">Methods</span></span>  
  
|<span data-ttu-id="82a47-107">Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-107">Method</span></span>|<span data-ttu-id="82a47-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82a47-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82a47-109">ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="82a47-110">In Szenarien für die ClickOnce-Manifest-basiertes verwendet, an die Anwendung in einer neuen Domäne aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="82a47-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="82a47-111">ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="82a47-112">Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="82a47-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="82a47-113">ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="82a47-114">Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="82a47-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="82a47-115">GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="82a47-116">Ruft einen Schnittstellenzeiger vom Typ [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) Hosts verwenden können, um Aspekte der common Language Runtime (CLR) anzupassen.</span><span class="sxs-lookup"><span data-stu-id="82a47-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="82a47-117">GetCurrentAppDomainId-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="82a47-118">Ruft den numerischen Bezeichner von die <xref:System.AppDomain> , die gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="82a47-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="82a47-119">SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="82a47-120">Legt die Host-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82a47-120">Sets the host control interface.</span></span> <span data-ttu-id="82a47-121">Rufen Sie `SetHostControl` vor dem Aufruf `Start`.</span><span class="sxs-lookup"><span data-stu-id="82a47-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="82a47-122">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="82a47-123">Initialisiert die CLR in einen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="82a47-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="82a47-124">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="82a47-125">Beendet die Ausführung von Code von der Runtime an.</span><span class="sxs-lookup"><span data-stu-id="82a47-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="82a47-126">UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="82a47-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="82a47-127">Entlädt die <xref:System.AppDomain> , die den angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="82a47-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a47-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82a47-128">Remarks</span></span>  
 <span data-ttu-id="82a47-129">Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], verwenden die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) Schnittstelle, um einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, und rufen Sie anschließend die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, um einen Zeiger auf `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="82a47-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="82a47-130">In früheren Versionen von .NET Framework, der Host Ruft einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="82a47-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="82a47-131">Um Implementierungen der Technologien bereitgestellt, die in .NET Framework, Version 2.0 zu gewährleisten, verwenden Sie `ICLRRuntimeHost` anstelle von `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="82a47-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82a47-132">Rufen Sie nicht die [starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) Methode, um ein Manifest-basierten Anwendung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="82a47-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="82a47-133">Wenn die `Start` -Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="82a47-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a47-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82a47-134">Requirements</span></span>  
 <span data-ttu-id="82a47-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82a47-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a47-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82a47-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82a47-137">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="82a47-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82a47-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82a47-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a47-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82a47-139">See Also</span></span>  
 [<span data-ttu-id="82a47-140">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="82a47-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="82a47-141">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="82a47-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="82a47-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82a47-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="82a47-143">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82a47-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="82a47-144">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="82a47-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="82a47-145">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="82a47-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
