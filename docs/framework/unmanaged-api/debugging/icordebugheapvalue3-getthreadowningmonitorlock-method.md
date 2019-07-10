---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4322a7e23c7085dadb3b2df6c1f72125aa685cef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756607"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="fda55-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="fda55-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="fda55-103">Gibt zurück, den verwalteten Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="fda55-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fda55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fda55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fda55-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="fda55-106">[out] Der verwaltete Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="fda55-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="fda55-107">[out] Die Anzahl wie oft dieser Thread die Sperre freizugeben, bevor sie zurückkehrt, ohne Besitzer werden müssten.</span><span class="sxs-lookup"><span data-stu-id="fda55-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fda55-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fda55-108">Return Value</span></span>  
 <span data-ttu-id="fda55-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fda55-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fda55-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fda55-110">HRESULT</span></span>|<span data-ttu-id="fda55-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fda55-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fda55-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fda55-112">S_OK</span></span>|<span data-ttu-id="fda55-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fda55-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="fda55-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fda55-114">S_FALSE</span></span>|<span data-ttu-id="fda55-115">Kein verwalteter Thread besitzt die Monitorsperre für dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="fda55-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fda55-116">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fda55-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fda55-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fda55-117">Remarks</span></span>  
 <span data-ttu-id="fda55-118">Wenn ein verwalteter Thread die Sperre der Überwachung für dieses Objekt besitzt:</span><span class="sxs-lookup"><span data-stu-id="fda55-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="fda55-119">Die Methode gibt S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="fda55-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="fda55-120">Das Threadobjekt ist gültig, bis der Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fda55-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="fda55-121">Wenn kein verwalteter Thread die Sperre der Überwachung für dieses Objekt besitzt `ppThread` und `pAcquisitionCount` bleiben unverändert, und die Methode gibt S_FALSE zurück.</span><span class="sxs-lookup"><span data-stu-id="fda55-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="fda55-122">Wenn `ppThread` oder `pAcquisitionCount` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fda55-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="fda55-123">Wenn ein Fehler auftritt, nicht ermittelt werden kann, die ggf. Thread die Sperre der Überwachung für dieses Objekt besitzt, gibt die Methode ein HRESULT, das Fehler weist darauf hin zurück.</span><span class="sxs-lookup"><span data-stu-id="fda55-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fda55-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fda55-124">Requirements</span></span>  
 <span data-ttu-id="fda55-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fda55-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fda55-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fda55-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fda55-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fda55-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fda55-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fda55-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda55-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fda55-129">See also</span></span>

- [<span data-ttu-id="fda55-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fda55-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fda55-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fda55-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
