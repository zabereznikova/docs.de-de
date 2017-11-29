---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3571f546f71515a980c5415e568ae85eb0863d42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="184ec-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="184ec-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="184ec-103">Gibt den verwalteten Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="184ec-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="184ec-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="184ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="184ec-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="184ec-106">[out] Der verwaltete Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="184ec-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="184ec-107">[out] Die Anzahl der Wiederholungen, die dieser Thread die Sperre aufzuheben, bevor zurückgegeben, die Besitzer werden müssten.</span><span class="sxs-lookup"><span data-stu-id="184ec-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="184ec-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="184ec-108">Return Value</span></span>  
 <span data-ttu-id="184ec-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="184ec-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="184ec-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="184ec-110">HRESULT</span></span>|<span data-ttu-id="184ec-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="184ec-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="184ec-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="184ec-112">S_OK</span></span>|<span data-ttu-id="184ec-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="184ec-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="184ec-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="184ec-114">S_FALSE</span></span>|<span data-ttu-id="184ec-115">Kein verwalteter Thread besitzt die Monitorsperre für dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="184ec-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="184ec-116">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="184ec-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="184ec-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="184ec-117">Remarks</span></span>  
 <span data-ttu-id="184ec-118">Wenn ein verwalteter Thread die Monitorsperre für dieses Objekt besitzt:</span><span class="sxs-lookup"><span data-stu-id="184ec-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="184ec-119">Die Methode gibt S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="184ec-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="184ec-120">Das Threadobjekt ist gültig, bis der Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="184ec-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="184ec-121">Wenn kein verwalteter Thread die Monitorsperre für dieses Objekt besitzt `ppThread` und `pAcquisitionCount` unverändert, und die Methode gibt "S_FALSE" zurück.</span><span class="sxs-lookup"><span data-stu-id="184ec-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="184ec-122">Wenn `ppThread` oder `pAcquisitionCount` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="184ec-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="184ec-123">Wenn ein Fehler auftritt, sodass nicht ermittelt werden kann, dem Thread die Monitorsperre für dieses Objekt besitzt, sofern vorhanden, gibt die Methode ein HRESULT, das Fehler weist darauf hin zurück.</span><span class="sxs-lookup"><span data-stu-id="184ec-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="184ec-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="184ec-124">Requirements</span></span>  
 <span data-ttu-id="184ec-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="184ec-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="184ec-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="184ec-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="184ec-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="184ec-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="184ec-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="184ec-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184ec-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="184ec-129">See Also</span></span>  
 [<span data-ttu-id="184ec-130">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="184ec-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="184ec-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="184ec-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
