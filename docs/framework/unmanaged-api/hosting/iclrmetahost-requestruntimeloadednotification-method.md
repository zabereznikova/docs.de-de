---
title: ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32eb92263685bc3be9f0c28dea88ecfa78c2b52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="3ef2b-102">ICLRMetaHost::RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="3ef2b-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="3ef2b-103">Stellt eine Rückruffunktion, die garantiert aufgerufen werden, wenn eine Version der common Language Runtime (CLR) zum ersten Mal geladen, aber noch nicht begonnen.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="3ef2b-104">Diese Methode hat Vorrang vor den [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef2b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ef2b-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ef2b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ef2b-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="3ef2b-107">[in] Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ef2b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ef2b-108">Return Value</span></span>  
 <span data-ttu-id="3ef2b-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3ef2b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ef2b-110">HRESULT</span></span>|<span data-ttu-id="3ef2b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ef2b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ef2b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ef2b-112">S_OK</span></span>|<span data-ttu-id="3ef2b-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="3ef2b-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3ef2b-114">E_POINTER</span></span>|<span data-ttu-id="3ef2b-115">`pCallbackFunction` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ef2b-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ef2b-116">Remarks</span></span>  
 <span data-ttu-id="3ef2b-117">Der Rückruf wird auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="3ef2b-118">Nur, wenn eine Laufzeit zum ersten Mal geladen wird, wird der Rückruf aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="3ef2b-119">Der Rückruf wird nicht für wiedereintrittsfähige lädt der gleichen Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="3ef2b-120">Für nicht wieder eintretender Laufzeit geladen wird werden Aufrufe an die Rückruffunktion serialisiert.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="3ef2b-121">Die Rückruffunktion besitzt den folgenden Prototyp:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="3ef2b-122">Die Rückruf-Funktionsprototypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="3ef2b-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="3ef2b-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="3ef2b-125">Wenn der Host beabsichtigt geladen oder dazu führen, dass eine andere zur Laufzeit in eine eintrittsinvariante Weise geladen werden die `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` Parameter bereitgestellten Funktion im Rückruf auf folgende Weise verwendet werden muss:</span><span class="sxs-lookup"><span data-stu-id="3ef2b-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="3ef2b-126">`pfnCallbackThreadSet`muss vom Thread aufgerufen werden, die ein Laden der Laufzeit verursachen können, bevor, eine solche Last versucht wird.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="3ef2b-127">`pfnCallbackThreadUnset`muss aufgerufen werden, wenn der Thread nicht mehr Laden der Laufzeit verursacht (und vor der Rückgabe aus der ersten Rückruf).</span><span class="sxs-lookup"><span data-stu-id="3ef2b-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="3ef2b-128">`pfnCallbackThreadSet`und `pfnCallbackThreadUnset` sind beide nicht wieder eintretender.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ef2b-129">Hosten von Anwendungen müssen nicht aufrufen `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` außerhalb des Bereichs der `pCallbackFunction` Parameter.</span><span class="sxs-lookup"><span data-stu-id="3ef2b-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef2b-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ef2b-130">Requirements</span></span>  
 <span data-ttu-id="3ef2b-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ef2b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ef2b-132">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3ef2b-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3ef2b-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3ef2b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ef2b-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ef2b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef2b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ef2b-135">See Also</span></span>  
 [<span data-ttu-id="3ef2b-136">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ef2b-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="3ef2b-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="3ef2b-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
