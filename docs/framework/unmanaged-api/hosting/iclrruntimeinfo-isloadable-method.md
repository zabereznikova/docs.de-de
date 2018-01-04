---
title: ICLRRuntimeInfo::IsLoadable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="bb4a7-102">ICLRRuntimeInfo::IsLoadable-Methode</span><span class="sxs-lookup"><span data-stu-id="bb4a7-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="bb4a7-103">Gibt an, ob der aktuelle Prozess ein, und berücksichtigt die Runtime diese Schnittstelle zugeordneten geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb4a7-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb4a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb4a7-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="bb4a7-106">[out] `true` Wenn diese Laufzeit, in den aktuellen Prozess geladen ist, andernfalls werden konnte `false`.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb4a7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb4a7-107">Return Value</span></span>  
 <span data-ttu-id="bb4a7-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bb4a7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb4a7-109">HRESULT</span></span>|<span data-ttu-id="bb4a7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb4a7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb4a7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb4a7-111">S_OK</span></span>|<span data-ttu-id="bb4a7-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="bb4a7-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="bb4a7-113">E_POINTER</span></span>|<span data-ttu-id="bb4a7-114">`pbLoadable` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb4a7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb4a7-115">Remarks</span></span>  
 <span data-ttu-id="bb4a7-116">Falls bereits einer anderen Laufzeit in den Prozess geladen wird und die Common Language Runtime diese Schnittstelle zugeordneten werden, für die Ausführung des prozessinternen Seite-an-Seite geladen kann, `pbLoadable` gibt `true`.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="bb4a7-117">Wenn die Seite-an-Seite in-Process, die zwei Laufzeiten ausgeführt werden können `pbLoadable` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="bb4a7-118">Die common Language Runtime (CLR) Version 4 kann z. B. nebeneinander im selben Prozess mit CLR, Version 2.0 oder CLR, Version 1.1 ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="bb4a7-119">CLR, Version 1.1 und CLR, Version 2.0 kann nicht in-Process-Seite-an-Seite ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="bb4a7-120">Wenn keine Laufzeiten in den Prozess geladen sind, gibt diese Methode immer `true`.</span><span class="sxs-lookup"><span data-stu-id="bb4a7-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb4a7-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb4a7-121">Requirements</span></span>  
 <span data-ttu-id="bb4a7-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb4a7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4a7-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bb4a7-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bb4a7-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb4a7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb4a7-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4a7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4a7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb4a7-126">See Also</span></span>  
 [<span data-ttu-id="bb4a7-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb4a7-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="bb4a7-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb4a7-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="bb4a7-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="bb4a7-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
