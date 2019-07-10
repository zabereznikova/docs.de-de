---
title: ICorDebugStackWalk::GetFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81c3eec9b33f51bd30cf8724eaf010d7cd0b6cd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760927"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="a0b56-102">ICorDebugStackWalk::GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="a0b56-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="a0b56-103">Ruft den aktuellen Frame in der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="a0b56-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0b56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0b56-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="a0b56-106">[in] Ein Zeiger auf die Adresse des erstellten Frame-Objekts, das den aktuellen Frame im Stapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0b56-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0b56-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0b56-107">Return Value</span></span>  
 <span data-ttu-id="a0b56-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a0b56-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a0b56-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0b56-109">HRESULT</span></span>|<span data-ttu-id="a0b56-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0b56-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0b56-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0b56-111">S_OK</span></span>|<span data-ttu-id="a0b56-112">Den aktuellen Frame wird von der Common Language Runtime wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0b56-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="a0b56-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0b56-113">E_FAIL</span></span>|<span data-ttu-id="a0b56-114">Der aktuelle Frame wurde nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0b56-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="a0b56-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a0b56-115">S_FALSE</span></span>|<span data-ttu-id="a0b56-116">Der aktuelle Frame ist ein systemeigener Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="a0b56-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="a0b56-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a0b56-117">E_INVALIDARG</span></span>|<span data-ttu-id="a0b56-118">`pFrame` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a0b56-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="a0b56-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="a0b56-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="a0b56-120">Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a0b56-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a0b56-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a0b56-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b56-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0b56-122">Remarks</span></span>  
 <span data-ttu-id="a0b56-123">`ICorDebugStackWalk` Gibt nur die tatsächliche Stapelrahmen zurück.</span><span class="sxs-lookup"><span data-stu-id="a0b56-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="a0b56-124">Verwenden der [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Methode, um internen Frames zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a0b56-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="a0b56-125">(Die internen Frames sind Datenstrukturen, die von der Laufzeit zum Speichern von temporären Daten auf dem Stapel abgelegt.)</span><span class="sxs-lookup"><span data-stu-id="a0b56-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b56-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0b56-126">Requirements</span></span>  
 <span data-ttu-id="a0b56-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b56-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b56-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0b56-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0b56-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0b56-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0b56-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b56-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b56-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0b56-131">See also</span></span>

- [<span data-ttu-id="a0b56-132">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0b56-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="a0b56-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a0b56-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0b56-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a0b56-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
