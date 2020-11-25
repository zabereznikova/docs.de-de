---
title: IHostCrst::Leave-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 0752afb42b8c512450b047a5e2e7e1ff34533487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729576"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="b282a-102">IHostCrst::Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="b282a-102">IHostCrst::Leave Method</span></span>

<span data-ttu-id="b282a-103">Verlässt den kritischen Abschnitt, der von der aktuellen Instanz von [IHostCrst](ihostcrst-interface.md)dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b282a-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b282a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b282a-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b282a-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b282a-105">Return Value</span></span>  
  
|<span data-ttu-id="b282a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b282a-106">HRESULT</span></span>|<span data-ttu-id="b282a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b282a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b282a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b282a-108">S_OK</span></span>|<span data-ttu-id="b282a-109">`Leave` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b282a-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="b282a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b282a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b282a-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b282a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b282a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b282a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b282a-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b282a-113">The call timed out.</span></span>|  
|<span data-ttu-id="b282a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b282a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b282a-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b282a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b282a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b282a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b282a-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b282a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b282a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b282a-118">E_FAIL</span></span>|<span data-ttu-id="b282a-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b282a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b282a-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="b282a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b282a-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b282a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b282a-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b282a-122">Remarks</span></span>  

 <span data-ttu-id="b282a-123">`Leave` ermöglicht der CLR, direkt mit der Threading Implementierung des Hosts zu kommunizieren, anstatt die entsprechende Win32- `LeaveCriticalSection` Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b282a-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="b282a-124">Ein Thread, der den Besitz des kritischen Abschnitts übernimmt, der durch die aktuelle Instanz dargestellt wird `IHostCrst` `Leave` , muss für jedes Mal, wenn er in diesen kritischen Abschnitt wechselt, einmal aufgerufen werden</span><span class="sxs-lookup"><span data-stu-id="b282a-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b282a-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b282a-125">Requirements</span></span>  

 <span data-ttu-id="b282a-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b282a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b282a-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b282a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b282a-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b282a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b282a-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b282a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b282a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b282a-130">See also</span></span>

- [<span data-ttu-id="b282a-131">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b282a-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b282a-132">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b282a-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="b282a-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b282a-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
