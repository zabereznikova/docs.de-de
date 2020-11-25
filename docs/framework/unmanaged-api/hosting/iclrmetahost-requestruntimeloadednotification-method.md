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
ms.openlocfilehash: ac40e203cf7d32c1fe30c9915bac3171139403e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723282"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="df10e-102">ICLRMetaHost::RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="df10e-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>

<span data-ttu-id="df10e-103">Stellt eine Rückruffunktion bereit, die garantiert aufgerufen wird, wenn eine Common Language Runtime (CLR)-Version zum ersten Mal geladen, aber noch nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="df10e-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="df10e-104">Diese Methode löst die [LockClrVersion](lockclrversion-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="df10e-104">This method supersedes the [LockClrVersion](lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df10e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="df10e-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df10e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="df10e-106">Parameters</span></span>  

 `pCallbackFunction`  
 <span data-ttu-id="df10e-107">in Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="df10e-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df10e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df10e-108">Return Value</span></span>  

 <span data-ttu-id="df10e-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="df10e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="df10e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df10e-110">HRESULT</span></span>|<span data-ttu-id="df10e-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="df10e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df10e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="df10e-112">S_OK</span></span>|<span data-ttu-id="df10e-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="df10e-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="df10e-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="df10e-114">E_POINTER</span></span>|<span data-ttu-id="df10e-115">`pCallbackFunction` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="df10e-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df10e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df10e-116">Remarks</span></span>  

 <span data-ttu-id="df10e-117">Der Rückruf funktioniert wie folgt:</span><span class="sxs-lookup"><span data-stu-id="df10e-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="df10e-118">Der Rückruf wird nur aufgerufen, wenn eine Laufzeit zum ersten Mal geladen wird.</span><span class="sxs-lookup"><span data-stu-id="df10e-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="df10e-119">Der Rückruf wird nicht für Wiedereintritts fähige Ladevorgänge derselben Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="df10e-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="df10e-120">Bei nicht wieder eintretende Lauf Zeit Ladevorgängen werden Aufrufe der Rückruffunktion serialisiert.</span><span class="sxs-lookup"><span data-stu-id="df10e-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="df10e-121">Die Rückruffunktion hat den folgenden Prototyp:</span><span class="sxs-lookup"><span data-stu-id="df10e-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="df10e-122">Die Rückruf Funktionsprototypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="df10e-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="df10e-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="df10e-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="df10e-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="df10e-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="df10e-125">Wenn der Host geladen werden soll oder eine andere Laufzeit in eine Einstiegs Weise geladen werden soll, `pfnCallbackThreadSet` müssen die-und- `pfnCallbackThreadUnset` Parameter, die in der Rückruffunktion bereitgestellt werden, wie folgt verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="df10e-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="df10e-126">`pfnCallbackThreadSet` muss vom Thread aufgerufen werden, der eine Lauf Zeit Auslastung verursachen kann, bevor ein solcher Ladevorgang versucht wird.</span><span class="sxs-lookup"><span data-stu-id="df10e-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="df10e-127">`pfnCallbackThreadUnset` muss aufgerufen werden, wenn der Thread eine solche Lauf Zeit Auslastung nicht mehr bewirkt (und bevor der anfängliche Rückruf zurückgegeben wird).</span><span class="sxs-lookup"><span data-stu-id="df10e-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="df10e-128">`pfnCallbackThreadSet` und `pfnCallbackThreadUnset` sind beide nicht Wiedereintritts fähig.</span><span class="sxs-lookup"><span data-stu-id="df10e-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df10e-129">Host Anwendungen dürfen nicht und außerhalb des Gültigkeits `pfnCallbackThreadSet` `pfnCallbackThreadUnset` Bereichs des- `pCallbackFunction` Parameters aufrufen.</span><span class="sxs-lookup"><span data-stu-id="df10e-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df10e-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df10e-130">Requirements</span></span>  

 <span data-ttu-id="df10e-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df10e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df10e-132">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="df10e-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df10e-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df10e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df10e-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df10e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df10e-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df10e-135">See also</span></span>

- [<span data-ttu-id="df10e-136">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df10e-136">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="df10e-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="df10e-137">Hosting</span></span>](index.md)
