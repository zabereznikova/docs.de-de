---
title: IHostTaskManager::EnterRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 1591a055200618f3e4951b5f6cf860dd3e71b44b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554357"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="0cdbe-102">IHostTaskManager::EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="0cdbe-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="0cdbe-103">Benachrichtigt den Host, dass ein Aufruf an eine nicht verwaltete Methode, z. b. eine Platt Form Aufruf Methode, die Ausführungs Steuerung an den Common Language Runtime (CLR) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cdbe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cdbe-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0cdbe-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0cdbe-105">Return Value</span></span>  
  
|<span data-ttu-id="0cdbe-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cdbe-106">HRESULT</span></span>|<span data-ttu-id="0cdbe-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cdbe-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cdbe-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cdbe-108">S_OK</span></span>|<span data-ttu-id="0cdbe-109">`EnterRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="0cdbe-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0cdbe-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0cdbe-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0cdbe-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0cdbe-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0cdbe-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-113">The call timed out.</span></span>|  
|<span data-ttu-id="0cdbe-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0cdbe-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0cdbe-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0cdbe-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0cdbe-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0cdbe-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0cdbe-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0cdbe-118">E_FAIL</span></span>|<span data-ttu-id="0cdbe-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0cdbe-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0cdbe-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0cdbe-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0cdbe-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0cdbe-123">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cdbe-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cdbe-124">Remarks</span></span>  
 <span data-ttu-id="0cdbe-125">`EnterRuntime` wird aufgerufen, um den Host zu benachrichtigen, dass eine nicht verwaltete Funktion, für die ein früherer Aufruf der [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) -Methode erfolgt ist, die Ausführung beendet hat und die Ausführungs Steuerung an die Laufzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cdbe-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) wird aufgerufen, um den Host zu benachrichtigen, dass eine nicht verwaltete Funktion, für die ein früherer Aufruf von `LeaveRuntime` erfolgt ist, den verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cdbe-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cdbe-127">Requirements</span></span>  
 <span data-ttu-id="0cdbe-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cdbe-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cdbe-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0cdbe-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cdbe-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0cdbe-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cdbe-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cdbe-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cdbe-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cdbe-132">See also</span></span>

- <span data-ttu-id="0cdbe-133">[Erweiterte COM-Interoperabilität](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0cdbe-133">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="0cdbe-134">Gewusst wie: Aufrufen von systemeigenen DLLs aus verwaltetem Code mithilfe von PInvoke</span><span class="sxs-lookup"><span data-stu-id="0cdbe-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="0cdbe-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdbe-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0cdbe-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdbe-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0cdbe-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdbe-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0cdbe-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdbe-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="0cdbe-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="0cdbe-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
