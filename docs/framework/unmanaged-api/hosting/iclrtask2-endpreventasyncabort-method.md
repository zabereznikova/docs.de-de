---
title: ICLRTask2::EndPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 7f8963403c60815bbf1cd3008ed7fec73d849fea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720255"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="53435-102">ICLRTask2::EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="53435-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>

<span data-ttu-id="53435-103">Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="53435-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53435-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="53435-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="53435-105">Return Value</span></span>  

 <span data-ttu-id="53435-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="53435-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="53435-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53435-107">HRESULT</span></span>|<span data-ttu-id="53435-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53435-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53435-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="53435-109">S_OK</span></span>|<span data-ttu-id="53435-110">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="53435-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="53435-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="53435-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="53435-112">Die-Methode wurde für einen Thread aufgerufen, der nicht der aktuelle Thread ist.</span><span class="sxs-lookup"><span data-stu-id="53435-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53435-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53435-113">Remarks</span></span>  

 <span data-ttu-id="53435-114">Durch den Aufruf dieser Methode wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread um 1 verringert.</span><span class="sxs-lookup"><span data-stu-id="53435-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="53435-115">Aufrufe von [ICLRTask2:: BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) und `EndPreventAsyncAbort` können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="53435-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="53435-116">Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.</span><span class="sxs-lookup"><span data-stu-id="53435-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="53435-117">Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="53435-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="53435-118">Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen.</span><span class="sxs-lookup"><span data-stu-id="53435-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="53435-119">`EndPreventAsyncAbort`Wenn Sie z. b. aufrufen, ohne zuerst aufrufen, `BeginPreventAsyncAbort` können Sie den-Wert auf Null setzen, wenn der virtuelle Computer ihn zuvor erhöht hat.</span><span class="sxs-lookup"><span data-stu-id="53435-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="53435-120">Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft.</span><span class="sxs-lookup"><span data-stu-id="53435-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="53435-121">Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="53435-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53435-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="53435-122">Requirements</span></span>  

 <span data-ttu-id="53435-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53435-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53435-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="53435-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53435-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="53435-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53435-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53435-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53435-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53435-127">See also</span></span>

- [<span data-ttu-id="53435-128">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="53435-128">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="53435-129">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53435-129">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="53435-130">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53435-130">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="53435-131">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53435-131">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="53435-132">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53435-132">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="53435-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53435-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
