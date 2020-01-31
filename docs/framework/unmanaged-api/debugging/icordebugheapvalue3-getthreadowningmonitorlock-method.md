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
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788621"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="d4031-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="d4031-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="d4031-103">Gibt den verwalteten Thread zurück, der die Monitor Sperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="d4031-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4031-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4031-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4031-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d4031-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="d4031-106">vorgenommen Der verwaltete Thread, der die Monitor Sperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="d4031-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="d4031-107">vorgenommen Gibt an, wie oft dieser Thread die Sperre freigeben müsste, bevor die Sperre aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="d4031-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4031-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4031-108">Return Value</span></span>  
 <span data-ttu-id="d4031-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4031-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d4031-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4031-110">HRESULT</span></span>|<span data-ttu-id="d4031-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4031-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4031-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4031-112">S_OK</span></span>|<span data-ttu-id="d4031-113">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d4031-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d4031-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d4031-114">S_FALSE</span></span>|<span data-ttu-id="d4031-115">Kein verwalteter Thread besitzt die Monitor Sperre für dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="d4031-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d4031-116">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d4031-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4031-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4031-117">Remarks</span></span>  
 <span data-ttu-id="d4031-118">Wenn ein verwalteter Thread die Monitor Sperre für dieses Objekt besitzt:</span><span class="sxs-lookup"><span data-stu-id="d4031-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="d4031-119">Die Methode gibt S_OK zurück.</span><span class="sxs-lookup"><span data-stu-id="d4031-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="d4031-120">Das Thread Objekt ist gültig, bis der Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4031-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="d4031-121">Wenn kein verwalteter Thread die Monitor Sperre für dieses Objekt besitzt, sind `ppThread` und `pAcquisitionCount` unverändert, und die Methode gibt S_FALSE zurück.</span><span class="sxs-lookup"><span data-stu-id="d4031-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="d4031-122">Wenn `ppThread` oder `pAcquisitionCount` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="d4031-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="d4031-123">Wenn ein Fehler auftritt, sodass nicht bestimmt werden kann, welcher Thread, sofern vorhanden, die Monitor Sperre für dieses Objekt besitzt, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d4031-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4031-124">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4031-124">Requirements</span></span>  
 <span data-ttu-id="d4031-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4031-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4031-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4031-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4031-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4031-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4031-128">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4031-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4031-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4031-129">See also</span></span>

- [<span data-ttu-id="d4031-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4031-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d4031-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d4031-131">Debugging</span></span>](index.md)
