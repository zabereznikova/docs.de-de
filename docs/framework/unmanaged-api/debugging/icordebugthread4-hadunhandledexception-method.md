---
title: ICorDebugThread4::HadUnhandledException-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.HadUnhandledException Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ea29fa02e74c204cde003b18520bf512b0d21d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="80185-102">ICorDebugThread4::HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="80185-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="80185-103">Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="80185-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80185-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80185-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80185-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80185-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="80185-106">[out] Ein Zeiger auf die Adresse des eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="80185-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80185-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80185-107">Return Value</span></span>  
 <span data-ttu-id="80185-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80185-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80185-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80185-109">HRESULT</span></span>|<span data-ttu-id="80185-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80185-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80185-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="80185-111">S_OK</span></span>|<span data-ttu-id="80185-112">Der Thread ist seit seiner Erstellung eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="80185-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="80185-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="80185-113">S_FALSE</span></span>|<span data-ttu-id="80185-114">Der Thread ist nie eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="80185-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80185-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80185-115">Remarks</span></span>  
 <span data-ttu-id="80185-116">Diese Methode gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="80185-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="80185-117">Nach der Zeit wird der Rückruf für nicht behandelte Ausnahme ausgelöst oder systemeigenes JIT-attach initiiert wird, diese Methode wird sichergestellt, dass S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80185-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="80185-118">Es gibt keine Garantie, die die [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) Methode gibt zurück, die nicht behandelte Ausnahme; allerdings es tritt ein, wenn der Prozess nicht noch nach Eingang des Ausnahmefehler Rückrufs oder nach fortgesetzt wurde systemeigenes JIT-attach.</span><span class="sxs-lookup"><span data-stu-id="80185-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="80185-119">Außerdem ist es möglich (wenn auch unwahrscheinlich), haben mehrere Threads durch eine nicht behandelte Ausnahme, die zum Zeitpunkt der systemeigenen JIT-attach ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="80185-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="80185-120">In einem solchen Fall besteht keine Möglichkeit zu bestimmen, welche Ausnahme ausgelöst, die JIT-attach zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="80185-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80185-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80185-121">Requirements</span></span>  
 <span data-ttu-id="80185-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80185-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80185-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80185-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80185-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80185-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80185-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80185-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80185-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80185-126">See Also</span></span>  
 [<span data-ttu-id="80185-127">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80185-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="80185-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="80185-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="80185-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="80185-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
