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
ms.openlocfilehash: 452635764794e01858baab10464a03c966a55271
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711936"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="0624b-102">ICorDebugStackWalk::GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="0624b-102">ICorDebugStackWalk::GetFrame Method</span></span>

<span data-ttu-id="0624b-103">Ruft den aktuellen Frame im [ICorDebug](icordebugstackwalk-interface.md) -Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="0624b-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0624b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0624b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0624b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0624b-105">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="0624b-106">in Ein Zeiger auf die Adresse des erstellten Frame Objekts, das den aktuellen Frame im Stapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="0624b-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0624b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0624b-107">Return Value</span></span>  

 <span data-ttu-id="0624b-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0624b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0624b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0624b-109">HRESULT</span></span>|<span data-ttu-id="0624b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0624b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0624b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0624b-111">S_OK</span></span>|<span data-ttu-id="0624b-112">Die Laufzeit hat den aktuellen Frame erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0624b-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="0624b-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0624b-113">E_FAIL</span></span>|<span data-ttu-id="0624b-114">Der aktuelle Frame wurde nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0624b-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="0624b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0624b-115">S_FALSE</span></span>|<span data-ttu-id="0624b-116">Der aktuelle Frame ist ein nativer Stapel Rahmen.</span><span class="sxs-lookup"><span data-stu-id="0624b-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="0624b-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0624b-117">E_INVALIDARG</span></span>|<span data-ttu-id="0624b-118">`pFrame` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="0624b-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="0624b-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="0624b-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="0624b-120">Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0624b-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0624b-121">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0624b-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0624b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0624b-122">Remarks</span></span>  

 <span data-ttu-id="0624b-123">`ICorDebugStackWalk` gibt nur tatsächliche Stapel Rahmen zurück.</span><span class="sxs-lookup"><span data-stu-id="0624b-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="0624b-124">Verwenden Sie die [ICorDebugThread3:: getactiveingeternalframes](icordebugthread3-getactiveinternalframes-method.md) -Methode, um interne Frames zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0624b-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="0624b-125">(Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.)</span><span class="sxs-lookup"><span data-stu-id="0624b-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0624b-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0624b-126">Requirements</span></span>  

 <span data-ttu-id="0624b-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0624b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0624b-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0624b-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0624b-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0624b-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0624b-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0624b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0624b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0624b-131">See also</span></span>

- [<span data-ttu-id="0624b-132">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0624b-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="0624b-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0624b-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0624b-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0624b-134">Debugging</span></span>](index.md)
