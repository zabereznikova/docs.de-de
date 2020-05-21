---
title: ICLRTask2::BeginPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 0da18c6850f393808d05dff8b1f19ac12b05bb86
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762889"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="6f7f3-102">ICLRTask2::BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="6f7f3-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="6f7f3-103">Verzögert neue Thread Abbruch Anforderungen, was dazu führt, dass Threads im aktuellen Thread abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f7f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f7f3-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6f7f3-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f7f3-105">Return Value</span></span>  
 <span data-ttu-id="6f7f3-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6f7f3-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f7f3-107">HRESULT</span></span>|<span data-ttu-id="6f7f3-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f7f3-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f7f3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f7f3-109">S_OK</span></span>|<span data-ttu-id="6f7f3-110">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="6f7f3-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="6f7f3-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="6f7f3-112">Die-Methode wurde für einen Thread aufgerufen, der nicht der aktuelle Thread ist.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f7f3-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f7f3-113">Remarks</span></span>  
 <span data-ttu-id="6f7f3-114">Durch den Aufruf dieser Methode wird der Delay-Thread-Abbruch-Leistungswert für den aktuellen Thread um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="6f7f3-115">Aufrufe von `BeginPreventAsyncAbort` und [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) können nicht eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="6f7f3-116">Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="6f7f3-117">Wenn dieser-Befehl nicht mit einem Aufrufen der-Methode gekoppelt ist `EndPreventAsyncAbort` , kann ein Zustand erreicht werden, in dem Thread Abbrüche nicht an den aktuellen Thread übermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="6f7f3-118">Die Verzögerung wird für einen Thread, der sich selbst abbricht, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="6f7f3-119">Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="6f7f3-120">Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="6f7f3-121">`EndPreventAsyncAbort`Wenn Sie z. b. aufrufen, ohne zuerst aufrufen, `BeginPreventAsyncAbort` können Sie den-Wert auf Null setzen, wenn der virtuelle Computer ihn zuvor erhöht hat.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="6f7f3-122">Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="6f7f3-123">Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="6f7f3-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f7f3-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f7f3-124">Requirements</span></span>  
 <span data-ttu-id="6f7f3-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f7f3-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f7f3-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6f7f3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f7f3-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6f7f3-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f7f3-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f7f3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7f3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f7f3-129">See also</span></span>

- [<span data-ttu-id="6f7f3-130">EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="6f7f3-130">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="6f7f3-131">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f7f3-131">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="6f7f3-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f7f3-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6f7f3-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f7f3-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6f7f3-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f7f3-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6f7f3-135">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f7f3-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
