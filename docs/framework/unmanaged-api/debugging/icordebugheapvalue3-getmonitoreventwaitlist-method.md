---
title: ICorDebugHeapValue3::GetMonitorEventWaitList-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a395579892ff2410865a4fcdd19cf20449b82b88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421071"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="4e625-102">ICorDebugHeapValue3::GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="4e625-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="4e625-103">Stellt eine geordnete Liste von Threads in der Warteschlange auf das Ereignis, das einen Monitorsperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4e625-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e625-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e625-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e625-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e625-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="4e625-106">[out] Der ICorDebugThreadEnum-Enumerator, der die geordnete Liste der Threads bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4e625-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e625-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e625-107">Return Value</span></span>  
 <span data-ttu-id="4e625-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e625-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4e625-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e625-109">HRESULT</span></span>|<span data-ttu-id="4e625-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e625-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e625-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e625-111">S_OK</span></span>|<span data-ttu-id="4e625-112">Die Liste ist nicht leer.</span><span class="sxs-lookup"><span data-stu-id="4e625-112">The list is not empty.</span></span>|  
|<span data-ttu-id="4e625-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4e625-113">S_FALSE</span></span>|<span data-ttu-id="4e625-114">Die Liste ist leer.</span><span class="sxs-lookup"><span data-stu-id="4e625-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4e625-115">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="4e625-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e625-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e625-116">Remarks</span></span>  
 <span data-ttu-id="4e625-117">Der erste Thread in der Liste ist der erste Thread, der durch den nächsten Aufruf freigegeben wird <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e625-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4e625-118">Der nächste Thread in der Liste wird der folgende Aufruf usw. veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4e625-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="4e625-119">Wenn die Liste nicht leer ist, gibt diese Methode S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="4e625-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="4e625-120">Wenn die Liste leer ist, gibt die Methode "S_FALSE" zurück. In diesem Fall ist die Enumeration noch gültig sind, obwohl es leer ist.</span><span class="sxs-lookup"><span data-stu-id="4e625-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="4e625-121">In beiden Fällen ist die Enumerationsschnittstelle nur für die Dauer des aktuellen Status "synchronisiert" verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e625-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="4e625-122">Verteilten die Thread-Schnittstellen sind jedoch gültig, bis der Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e625-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="4e625-123">Wenn `ppThreadEnum` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4e625-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="4e625-124">Wenn ein Fehler auftritt, sodass nicht ermittelt werden kann, die ggf. Threads für den Monitor warten gibt die Methode ein HRESULT, das Fehler weist darauf hin.</span><span class="sxs-lookup"><span data-stu-id="4e625-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e625-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e625-125">Requirements</span></span>  
 <span data-ttu-id="4e625-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e625-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e625-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e625-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e625-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e625-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e625-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e625-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e625-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e625-130">See Also</span></span>  
 [<span data-ttu-id="4e625-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4e625-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4e625-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4e625-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
