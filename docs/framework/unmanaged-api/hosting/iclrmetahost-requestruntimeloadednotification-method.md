---
title: ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140899"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="9331f-102">ICLRMetaHost::RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="9331f-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="9331f-103">Stellt eine Rückruffunktion bereit, die garantiert aufgerufen wird, wenn eine Common Language Runtime (CLR)-Version zum ersten Mal geladen, aber noch nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="9331f-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="9331f-104">Diese Methode löst die [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="9331f-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9331f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9331f-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9331f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9331f-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="9331f-107">in Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="9331f-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9331f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9331f-108">Return Value</span></span>  
 <span data-ttu-id="9331f-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9331f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9331f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9331f-110">HRESULT</span></span>|<span data-ttu-id="9331f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9331f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9331f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9331f-112">S_OK</span></span>|<span data-ttu-id="9331f-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9331f-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9331f-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9331f-114">E_POINTER</span></span>|<span data-ttu-id="9331f-115">`pCallbackFunction` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9331f-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9331f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9331f-116">Remarks</span></span>  
 <span data-ttu-id="9331f-117">Der Rückruf funktioniert wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9331f-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="9331f-118">Der Rückruf wird nur aufgerufen, wenn eine Laufzeit zum ersten Mal geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9331f-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="9331f-119">Der Rückruf wird nicht für Wiedereintritts fähige Ladevorgänge derselben Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9331f-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="9331f-120">Bei nicht wieder eintretende Lauf Zeit Ladevorgängen werden Aufrufe der Rückruffunktion serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9331f-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="9331f-121">Die Rückruffunktion hat den folgenden Prototyp:</span><span class="sxs-lookup"><span data-stu-id="9331f-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="9331f-122">Die Rückruf Funktionsprototypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9331f-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="9331f-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="9331f-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="9331f-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="9331f-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="9331f-125">Wenn der Host geladen werden soll oder eine andere Laufzeit in eine Einstiegs Weise geladen werden soll, müssen die in der Rückruffunktion bereitgestellten `pfnCallbackThreadSet`-und `pfnCallbackThreadUnset` Parameter wie folgt verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="9331f-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="9331f-126">`pfnCallbackThreadSet` müssen von dem Thread aufgerufen werden, der eine Lauf Zeit Auslastung verursachen kann, bevor ein solcher Ladevorgang versucht wird.</span><span class="sxs-lookup"><span data-stu-id="9331f-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="9331f-127">`pfnCallbackThreadUnset` müssen aufgerufen werden, wenn der Thread eine solche Lauf Zeit Auslastung nicht mehr bewirkt (und bevor der anfängliche Rückruf zurückgegeben wird).</span><span class="sxs-lookup"><span data-stu-id="9331f-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="9331f-128">`pfnCallbackThreadSet` und `pfnCallbackThreadUnset` sind nicht Wiedereintritts fähig.</span><span class="sxs-lookup"><span data-stu-id="9331f-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9331f-129">Host Anwendungen dürfen `pfnCallbackThreadSet` nicht aufrufen und `pfnCallbackThreadUnset` außerhalb des Bereichs des `pCallbackFunction`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="9331f-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9331f-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9331f-130">Requirements</span></span>  
 <span data-ttu-id="9331f-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9331f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9331f-132">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="9331f-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9331f-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9331f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9331f-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9331f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9331f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9331f-135">See also</span></span>

- [<span data-ttu-id="9331f-136">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9331f-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="9331f-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="9331f-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
