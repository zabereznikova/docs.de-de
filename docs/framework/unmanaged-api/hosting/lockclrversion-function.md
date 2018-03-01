---
title: LockClrVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a58d7e99f545026f6f133901ef35a1f9b9fabc7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lockclrversion-function"></a><span data-ttu-id="16c23-102">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="16c23-102">LockClrVersion Function</span></span>
<span data-ttu-id="16c23-103">Ermöglicht den Host kann bestimmen, welche Version der common Language Runtime (CLR) innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="16c23-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="16c23-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="16c23-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c23-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="16c23-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16c23-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="16c23-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="16c23-107">[in] Die Funktion, die von der CLR bei der Initialisierung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16c23-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="16c23-108">[in] Die Funktion, die vom Host der CLR zu informieren, dass die Initialisierung aufgerufen werden, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="16c23-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="16c23-109">[in] Die Funktion, die vom Host der CLR zu informieren, dass die Initialisierung aufgerufen werden, ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="16c23-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16c23-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16c23-110">Return Value</span></span>  
 <span data-ttu-id="16c23-111">Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="16c23-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="16c23-112">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="16c23-112">Return code</span></span>|<span data-ttu-id="16c23-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16c23-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="16c23-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="16c23-114">S_OK</span></span>|<span data-ttu-id="16c23-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="16c23-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="16c23-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="16c23-116">E_INVALIDARG</span></span>|<span data-ttu-id="16c23-117">Eine oder mehrere der Argumente ist null.</span><span class="sxs-lookup"><span data-stu-id="16c23-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16c23-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16c23-118">Remarks</span></span>  
 <span data-ttu-id="16c23-119">Der Host ruft `LockClrVersion` vor dem Initialisieren der CLR.</span><span class="sxs-lookup"><span data-stu-id="16c23-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="16c23-120">`LockClrVersion`akzeptiert drei Parameter, die Rückrufe vom Typ sind [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="16c23-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="16c23-121">Dieser Typ ist wie folgt definiert.</span><span class="sxs-lookup"><span data-stu-id="16c23-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="16c23-122">Die folgenden Schritte erfolgen bei der Initialisierung der Runtime:</span><span class="sxs-lookup"><span data-stu-id="16c23-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="16c23-123">Der Host ruft [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder einer anderen Laufzeit Initialization Funktionen.</span><span class="sxs-lookup"><span data-stu-id="16c23-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="16c23-124">Alternativ konnte den Host die Laufzeit unter Verwendung der Aktivierung von COM-Objekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="16c23-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="16c23-125">Die Laufzeit ruft die Funktion, die gemäß der `hostCallback` Parameter.</span><span class="sxs-lookup"><span data-stu-id="16c23-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="16c23-126">Die Funktion anhand des `hostCallback` dann wird die folgende Sequenz von aufrufen:</span><span class="sxs-lookup"><span data-stu-id="16c23-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="16c23-127">Die angegebene Funktion die `pBeginHostSetup` Parameter.</span><span class="sxs-lookup"><span data-stu-id="16c23-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   <span data-ttu-id="16c23-128">`CorBindToRuntimeEx`(oder eine andere Funktion der Common Language Runtime-Initialisierung).</span><span class="sxs-lookup"><span data-stu-id="16c23-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="16c23-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="16c23-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="16c23-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="16c23-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="16c23-131">Die angegebene Funktion die `pEndHostSetup` Parameter.</span><span class="sxs-lookup"><span data-stu-id="16c23-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="16c23-132">Alle Aufrufe von `pBeginHostSetup` auf `pEndHostSetup` muss auf einem einzigen Thread oder Fiber mit demselben logischen Stapel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="16c23-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="16c23-133">Dieser Thread kann anderen als den Thread auf dem `hostCallback` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="16c23-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c23-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16c23-134">Requirements</span></span>  
 <span data-ttu-id="16c23-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16c23-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c23-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16c23-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16c23-137">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="16c23-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16c23-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c23-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c23-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c23-139">See Also</span></span>  
 [<span data-ttu-id="16c23-140">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="16c23-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
