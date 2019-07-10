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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e7c1de620979b387e969f4b8c9f17f493e7bcb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776542"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="4dcd1-102">ICLRMetaHost::RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="4dcd1-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="4dcd1-103">Bietet eine Rückruffunktion, die garantiert aufgerufen werden, wenn eine Version der common Language Runtime (CLR) zum ersten Mal geladen, aber noch nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="4dcd1-104">Diese Methode ersetzt die [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcd1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dcd1-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dcd1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4dcd1-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="4dcd1-107">[in] Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dcd1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4dcd1-108">Return Value</span></span>  
 <span data-ttu-id="4dcd1-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4dcd1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dcd1-110">HRESULT</span></span>|<span data-ttu-id="4dcd1-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4dcd1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dcd1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dcd1-112">S_OK</span></span>|<span data-ttu-id="4dcd1-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="4dcd1-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4dcd1-114">E_POINTER</span></span>|<span data-ttu-id="4dcd1-115">`pCallbackFunction` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dcd1-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4dcd1-116">Remarks</span></span>  
 <span data-ttu-id="4dcd1-117">Der Rückruf funktioniert wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="4dcd1-118">Der Rückruf erfolgt nur, wenn eine Laufzeit zum ersten Mal geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="4dcd1-119">Der Rückruf ist nicht für wiedereintrittsfähige lädt der gleichen Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="4dcd1-120">Für nicht wieder eintretender Laufzeit geladen wird werden Aufrufe an die Rückruffunktion serialisiert.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="4dcd1-121">Die Callback-Funktion hat den folgenden Prototyp:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="4dcd1-122">Die Rückruf-Funktionsprototypen lauten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="4dcd1-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="4dcd1-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="4dcd1-125">Wenn der Host beabsichtigt zu laden oder dazu führen, dass eine andere Runtime auf eine Weise wiedereintrittsfähige geladen werden die `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` Parameter bereitgestellte Funktion in der Rückruffunktion auf folgende Weise verwendet werden muss:</span><span class="sxs-lookup"><span data-stu-id="4dcd1-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="4dcd1-126">`pfnCallbackThreadSet` muss durch den Thread aufgerufen werden, die Laden der Laufzeit führen kann, bevor, eine solche Last versucht wird.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="4dcd1-127">`pfnCallbackThreadUnset` muss aufgerufen werden, wenn der Thread nicht mehr Laden der Laufzeit bewirkt (und vor der Rückgabe aus dem ersten Rückruf).</span><span class="sxs-lookup"><span data-stu-id="4dcd1-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="4dcd1-128">`pfnCallbackThreadSet` und `pfnCallbackThreadUnset` sind beide nicht wiedereintrittsfähig.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dcd1-129">Hosten von Anwendungen müssen nicht aufrufen, `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` außerhalb des Bereichs der `pCallbackFunction` Parameter.</span><span class="sxs-lookup"><span data-stu-id="4dcd1-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dcd1-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dcd1-130">Requirements</span></span>  
 <span data-ttu-id="4dcd1-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dcd1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dcd1-132">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4dcd1-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4dcd1-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4dcd1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dcd1-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dcd1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcd1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dcd1-135">See also</span></span>

- [<span data-ttu-id="4dcd1-136">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dcd1-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="4dcd1-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="4dcd1-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
