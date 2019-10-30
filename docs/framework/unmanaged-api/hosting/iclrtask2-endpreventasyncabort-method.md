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
ms.openlocfilehash: 8ae66e0bf96138e5bc2f33e4c14ad86e7dabc6b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124551"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="72e9e-102">ICLRTask2::EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="72e9e-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="72e9e-103">Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="72e9e-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72e9e-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="72e9e-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="72e9e-105">Return Value</span></span>  
 <span data-ttu-id="72e9e-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="72e9e-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="72e9e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72e9e-107">HRESULT</span></span>|<span data-ttu-id="72e9e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72e9e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72e9e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="72e9e-109">S_OK</span></span>|<span data-ttu-id="72e9e-110">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="72e9e-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="72e9e-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="72e9e-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="72e9e-112">Die-Methode wurde für einen Thread aufgerufen, der nicht der aktuelle Thread ist.</span><span class="sxs-lookup"><span data-stu-id="72e9e-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72e9e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72e9e-113">Remarks</span></span>  
 <span data-ttu-id="72e9e-114">Durch den Aufruf dieser Methode wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread um 1 verringert.</span><span class="sxs-lookup"><span data-stu-id="72e9e-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="72e9e-115">Aufrufe von [ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) und `EndPreventAsyncAbort` können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="72e9e-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="72e9e-116">Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.</span><span class="sxs-lookup"><span data-stu-id="72e9e-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="72e9e-117">Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="72e9e-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="72e9e-118">Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen.</span><span class="sxs-lookup"><span data-stu-id="72e9e-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="72e9e-119">Wenn Sie z. b. `EndPreventAsyncAbort` aufrufen, ohne zuerst `BeginPreventAsyncAbort` aufrufen, können Sie den-Wert auf NULL festlegen, wenn der virtuelle Computer ihn zuvor erhöht hat.</span><span class="sxs-lookup"><span data-stu-id="72e9e-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="72e9e-120">Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft.</span><span class="sxs-lookup"><span data-stu-id="72e9e-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="72e9e-121">Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="72e9e-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e9e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72e9e-122">Requirements</span></span>  
 <span data-ttu-id="72e9e-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72e9e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e9e-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="72e9e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72e9e-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="72e9e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72e9e-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e9e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e9e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e9e-127">See also</span></span>

- [<span data-ttu-id="72e9e-128">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="72e9e-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="72e9e-129">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e9e-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="72e9e-130">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e9e-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="72e9e-131">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e9e-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="72e9e-132">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e9e-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="72e9e-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="72e9e-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
