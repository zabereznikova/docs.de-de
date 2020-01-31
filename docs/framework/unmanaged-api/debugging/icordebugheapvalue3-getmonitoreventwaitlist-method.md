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
ms.openlocfilehash: 15900fab59d172ada67d8aefeab698e1b44f808e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794391"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="8b8be-102">ICorDebugHeapValue3::GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="8b8be-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="8b8be-103">Stellt eine geordnete Liste von Threads bereit, die für das-Ereignis in die Warteschlange eingereiht werden, das einer Monitor Sperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8b8be-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b8be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b8be-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8b8be-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="8b8be-106">[out] Der ICorDebugThreadEnum-Enumerator, der die geordnete Liste der Threads bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8b8be-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b8be-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b8be-107">Return Value</span></span>  
 <span data-ttu-id="8b8be-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b8be-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8b8be-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b8be-109">HRESULT</span></span>|<span data-ttu-id="8b8be-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b8be-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b8be-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b8be-111">S_OK</span></span>|<span data-ttu-id="8b8be-112">Die Liste ist nicht leer.</span><span class="sxs-lookup"><span data-stu-id="8b8be-112">The list is not empty.</span></span>|  
|<span data-ttu-id="8b8be-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8b8be-113">S_FALSE</span></span>|<span data-ttu-id="8b8be-114">Die Liste ist leer.</span><span class="sxs-lookup"><span data-stu-id="8b8be-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="8b8be-115">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="8b8be-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b8be-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b8be-116">Remarks</span></span>  
 <span data-ttu-id="8b8be-117">Der erste Thread in der Liste ist der erste Thread, der vom nächsten <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>-Auflistungs-aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8b8be-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8b8be-118">Der nächste Thread in der Liste wird für den folgenden-Befehl freigegeben, usw.</span><span class="sxs-lookup"><span data-stu-id="8b8be-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="8b8be-119">Wenn die Liste nicht leer ist, gibt diese Methode S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="8b8be-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="8b8be-120">Wenn die Liste leer ist, gibt die Methode S_FALSE zurück. in diesem Fall ist die Enumeration weiterhin gültig, obwohl Sie leer ist.</span><span class="sxs-lookup"><span data-stu-id="8b8be-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="8b8be-121">In beiden Fällen kann die Enumerationsschnittstelle nur für die Dauer des aktuellen synchronisierten Zustands verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b8be-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="8b8be-122">Die von ihm ausgegebene Schnittstellen des Threads sind jedoch gültig, bis der Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b8be-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="8b8be-123">Wenn `ppThreadEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="8b8be-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="8b8be-124">Wenn ein Fehler auftritt, sodass nicht bestimmt werden kann, welche Threads ggf. auf den Monitor warten, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8b8be-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b8be-125">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b8be-125">Requirements</span></span>  
 <span data-ttu-id="8b8be-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b8be-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b8be-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b8be-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b8be-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b8be-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b8be-129">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b8be-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8be-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b8be-130">See also</span></span>

- [<span data-ttu-id="8b8be-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8b8be-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8b8be-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8b8be-132">Debugging</span></span>](index.md)
