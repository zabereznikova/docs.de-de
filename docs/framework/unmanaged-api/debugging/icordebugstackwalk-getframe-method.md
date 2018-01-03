---
title: ICorDebugStackWalk::GetFrame-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetFrame Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c095afd0513360876e5330a130a4d938e30f8db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="92e0d-102">ICorDebugStackWalk::GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="92e0d-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="92e0d-103">Ruft den aktuellen Frame in der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="92e0d-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92e0d-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92e0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92e0d-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="92e0d-106">[in] Ein Zeiger auf die Adresse des erstellten Frameobjekt, das den aktuellen Frame im Stapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="92e0d-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92e0d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="92e0d-107">Return Value</span></span>  
 <span data-ttu-id="92e0d-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="92e0d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="92e0d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92e0d-109">HRESULT</span></span>|<span data-ttu-id="92e0d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92e0d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92e0d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="92e0d-111">S_OK</span></span>|<span data-ttu-id="92e0d-112">Den aktuellen Frame wird von der Common Language Runtime wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="92e0d-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="92e0d-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92e0d-113">E_FAIL</span></span>|<span data-ttu-id="92e0d-114">Der aktuelle Frame wurde nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="92e0d-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="92e0d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="92e0d-115">S_FALSE</span></span>|<span data-ttu-id="92e0d-116">Der aktuelle Frame ist ein systemeigener Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="92e0d-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="92e0d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="92e0d-117">E_INVALIDARG</span></span>|<span data-ttu-id="92e0d-118">`pFrame` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="92e0d-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="92e0d-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="92e0d-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="92e0d-120">Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="92e0d-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="92e0d-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="92e0d-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92e0d-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92e0d-122">Remarks</span></span>  
 <span data-ttu-id="92e0d-123">`ICorDebugStackWalk`Gibt nur die tatsächliche Stapelrahmen zurück.</span><span class="sxs-lookup"><span data-stu-id="92e0d-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="92e0d-124">Verwenden der [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Methode, um interne Frames zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="92e0d-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="92e0d-125">(Internen Frames sind Datenstrukturen, die von der Runtime zum Speichern temporärer Daten auf den Stapel verschoben.)</span><span class="sxs-lookup"><span data-stu-id="92e0d-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e0d-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92e0d-126">Requirements</span></span>  
 <span data-ttu-id="92e0d-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92e0d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e0d-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92e0d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92e0d-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92e0d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92e0d-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e0d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e0d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92e0d-131">See Also</span></span>  
 [<span data-ttu-id="92e0d-132">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92e0d-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="92e0d-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="92e0d-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="92e0d-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="92e0d-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
