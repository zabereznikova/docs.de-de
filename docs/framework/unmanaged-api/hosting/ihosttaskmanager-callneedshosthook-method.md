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
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176291"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="db35b-102">IHostTaskManager::CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="db35b-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="db35b-103">Ermöglicht dem Host, anzugeben, ob die Common Language Runtime (CLR) den angegebenen Aufruf an eine nicht verwaltete Funktion inlineisieren kann.</span><span class="sxs-lookup"><span data-stu-id="db35b-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db35b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db35b-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db35b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db35b-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="db35b-106">[in] Die Adresse in der zugeordneten portablen ausführbaren Datei (PE) der nicht verwalteten Funktion, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="db35b-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="db35b-107">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den Aufruf hooken muss.</span><span class="sxs-lookup"><span data-stu-id="db35b-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db35b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db35b-108">Return Value</span></span>  
  
|<span data-ttu-id="db35b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db35b-109">HRESULT</span></span>|<span data-ttu-id="db35b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db35b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db35b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="db35b-111">S_OK</span></span>|<span data-ttu-id="db35b-112">`CallNeedsHostHook`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="db35b-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="db35b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db35b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db35b-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="db35b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db35b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db35b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db35b-116">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="db35b-116">The call timed out.</span></span>|  
|<span data-ttu-id="db35b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db35b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db35b-118">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="db35b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db35b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db35b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db35b-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="db35b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db35b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db35b-121">E_FAIL</span></span>|<span data-ttu-id="db35b-122">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db35b-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="db35b-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db35b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db35b-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="db35b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db35b-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="db35b-125">Remarks</span></span>  
 <span data-ttu-id="db35b-126">Um die Codeausführung zu optimieren, führt die CLR während der Kompilierung eine Analyse der einzelnen Plattformaufrufaufrufen durch, um zu bestimmen, ob der Aufruf inline ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="db35b-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="db35b-127">`CallNeedsHostHook`ermöglicht es dem Host, diese Entscheidung zu überschreiben, indem er verlangt, dass ein Aufruf einer nicht verwalteten Funktion hooked wird.</span><span class="sxs-lookup"><span data-stu-id="db35b-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="db35b-128">Wenn der Host einen Hook benötigt, inlinet die Laufzeit den Aufruf nicht.</span><span class="sxs-lookup"><span data-stu-id="db35b-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="db35b-129">Der Host benötigt in der Regel einen Hook, an dem er einen Gleitkommastatus anpassen muss, oder wenn er eine Benachrichtigung erhält, dass ein Anruf in einen Zustand eintritt, in dem der Host die Speicheranforderungen der Laufzeit oder die gesperrten Sperren nicht nachverfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="db35b-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="db35b-130">Wenn der Host erfordert, dass der Aufruf hooked wird, benachrichtigt die Laufzeit den Host von Übergängen zu und von verwaltetem Code, indem aufrufe zu [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)und [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db35b-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db35b-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="db35b-131">Requirements</span></span>  
 <span data-ttu-id="db35b-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db35b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db35b-133">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db35b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db35b-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db35b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db35b-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db35b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db35b-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db35b-136">See also</span></span>

- [<span data-ttu-id="db35b-137">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db35b-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="db35b-138">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db35b-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="db35b-139">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db35b-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="db35b-140">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db35b-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
