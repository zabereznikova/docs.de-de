---
title: ICLRRuntimeInfo::IsLoadable-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52257b30b8172b80f968df25115956b6995c1552
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771734"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="e66c8-102">ICLRRuntimeInfo::IsLoadable-Methode</span><span class="sxs-lookup"><span data-stu-id="e66c8-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="e66c8-103">Gibt an, ob der aktuelle Prozess, die Berücksichtigung die Runtime, die dieser Schnittstelle zugeordnet geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="e66c8-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e66c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e66c8-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e66c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e66c8-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="e66c8-106">[out] `true` , wenn diese Runtime in den aktuellen Prozess geladen ist, andernfalls möglicherweise `false`.</span><span class="sxs-lookup"><span data-stu-id="e66c8-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e66c8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e66c8-107">Return Value</span></span>  
 <span data-ttu-id="e66c8-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e66c8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e66c8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e66c8-109">HRESULT</span></span>|<span data-ttu-id="e66c8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e66c8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e66c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e66c8-111">S_OK</span></span>|<span data-ttu-id="e66c8-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e66c8-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="e66c8-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e66c8-113">E_POINTER</span></span>|<span data-ttu-id="e66c8-114">`pbLoadable` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e66c8-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e66c8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e66c8-115">Remarks</span></span>  
 <span data-ttu-id="e66c8-116">Wenn eine andere Laufzeit bereits in den Prozess geladen wird und die Laufzeit, die dieser Schnittstelle zugeordnet zur in-Process-Seite-an-Seite-Ausführung geladen werden kann `pbLoadable` gibt `true`.</span><span class="sxs-lookup"><span data-stu-id="e66c8-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="e66c8-117">Wenn die Seite-an-Seite in-Process, die zwei Laufzeiten ausgeführt werden können `pbLoadable` gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="e66c8-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="e66c8-118">Die common Language Runtime (CLR), Version 4 kann z. B. Seite-an-Seite im gleichen Prozess mit CLR, Version 2.0 oder CLR-Version 1.1 ausführen.</span><span class="sxs-lookup"><span data-stu-id="e66c8-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="e66c8-119">CLR, Version 1.1 und der CLR, Version 2.0 kann nicht jedoch in-Process-Seite-an-Seite ausführen.</span><span class="sxs-lookup"><span data-stu-id="e66c8-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="e66c8-120">Wenn keine Laufzeiten, die in den Prozess geladen sind, gibt diese Methode immer `true`.</span><span class="sxs-lookup"><span data-stu-id="e66c8-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e66c8-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e66c8-121">Requirements</span></span>  
 <span data-ttu-id="e66c8-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e66c8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e66c8-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e66c8-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e66c8-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e66c8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e66c8-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e66c8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66c8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e66c8-126">See also</span></span>

- [<span data-ttu-id="e66c8-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e66c8-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e66c8-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e66c8-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e66c8-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="e66c8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
