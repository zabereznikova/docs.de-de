---
title: IHostTaskManager::CallNeedsHostHook-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 5bc5752d4d2b772b1d18f438c4daaa1b8938da9e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842347"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="8e669-102">IHostTaskManager::CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="8e669-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="8e669-103">Ermöglicht dem Host, anzugeben, ob die Common Language Runtime (CLR) den angegebenen aufrufenden Befehl an eine nicht verwaltete Funktion Inline bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="8e669-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e669-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e669-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e669-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e669-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="8e669-106">in Die Adresse in der zugeordneten PE-Datei (portable ausführbare Datei) der nicht verwalteten Funktion, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e669-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="8e669-107">vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den aufzurufenden-aufzurufenden erfordert.</span><span class="sxs-lookup"><span data-stu-id="8e669-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e669-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8e669-108">Return Value</span></span>  
  
|<span data-ttu-id="8e669-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e669-109">HRESULT</span></span>|<span data-ttu-id="8e669-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e669-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e669-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e669-111">S_OK</span></span>|<span data-ttu-id="8e669-112">`CallNeedsHostHook`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e669-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="8e669-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e669-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e669-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8e669-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e669-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e669-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e669-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8e669-116">The call timed out.</span></span>|  
|<span data-ttu-id="8e669-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e669-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e669-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8e669-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e669-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e669-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e669-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8e669-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e669-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e669-121">E_FAIL</span></span>|<span data-ttu-id="8e669-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8e669-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="8e669-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8e669-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e669-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8e669-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e669-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e669-125">Remarks</span></span>  
 <span data-ttu-id="8e669-126">Um die Codeausführung zu optimieren, führt die CLR während der Kompilierung eine Analyse der einzelnen Platt Form Aufrufe durch, um zu bestimmen, ob der Aufruf Inline sein kann.</span><span class="sxs-lookup"><span data-stu-id="8e669-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="8e669-127">`CallNeedsHostHook`ermöglicht es dem Host, diese Entscheidung zu überschreiben, indem gefordert wird, dass ein aufzurufende nicht verwaltete Funktion eingebunden wird.</span><span class="sxs-lookup"><span data-stu-id="8e669-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="8e669-128">Wenn der Host einen Hook erfordert, wird der-Befehl von der Laufzeit nicht Inline aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e669-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="8e669-129">Der Host erfordert in der Regel einen Hook, bei dem ein Gleit Komma Zustand angepasst werden muss, oder nach dem Empfang einer Benachrichtigung, dass ein-Befehl in einen Zustand versetzt wird, in dem der Host die Anforderungen für den Arbeitsspeicher oder die erforderlichen Sperren der Laufzeit nicht nachverfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="8e669-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="8e669-130">Wenn der Host erfordert, dass der Aufruf eingebunden ist, benachrichtigt die Common Language Runtime den Host über Übergänge zum und von verwaltetem Code mithilfe von Aufrufen von " [deterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)", " [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)", " [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)" und " [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)".</span><span class="sxs-lookup"><span data-stu-id="8e669-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e669-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e669-131">Requirements</span></span>  
 <span data-ttu-id="8e669-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e669-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e669-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8e669-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e669-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8e669-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e669-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e669-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e669-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e669-136">See also</span></span>

- [<span data-ttu-id="8e669-137">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e669-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8e669-138">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e669-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8e669-139">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e669-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8e669-140">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e669-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
