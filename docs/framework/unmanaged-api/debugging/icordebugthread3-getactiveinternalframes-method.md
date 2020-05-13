---
title: ICorDebugThread3::GetActiveInternalFrames-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 953b7c1cb5e471072776fe03e53a46d3ff19c0ac
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379853"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="0134a-102">ICorDebugThread3::GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="0134a-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="0134a-103">Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.</span><span class="sxs-lookup"><span data-stu-id="0134a-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0134a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0134a-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0134a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0134a-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="0134a-106">in Die Anzahl der in erwarteten internen Frames `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="0134a-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="0134a-107">vorgenommen Ein Zeiger auf einen-Wert `ULONG32` , der die Anzahl der internen Frames im Stapel enthält.</span><span class="sxs-lookup"><span data-stu-id="0134a-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="0134a-108">[in, out] Ein Zeiger auf die Adresse eines Arrays interner Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="0134a-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0134a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0134a-109">Return Value</span></span>  
 <span data-ttu-id="0134a-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0134a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0134a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0134a-111">HRESULT</span></span>|<span data-ttu-id="0134a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0134a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0134a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0134a-113">S_OK</span></span>|<span data-ttu-id="0134a-114">Das [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="0134a-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="0134a-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0134a-115">E_INVALIDARG</span></span>|<span data-ttu-id="0134a-116">`cInternalFrames`ist nicht NULL `ppInternalFrames` , und ist `null` , oder `pcInternalFrames` ist `null` .</span><span class="sxs-lookup"><span data-stu-id="0134a-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="0134a-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="0134a-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="0134a-118">`ppInternalFrames`ist kleiner als die Anzahl interner Frames.</span><span class="sxs-lookup"><span data-stu-id="0134a-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0134a-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0134a-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0134a-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0134a-120">Remarks</span></span>  
 <span data-ttu-id="0134a-121">Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="0134a-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="0134a-122">Beim ersten Aufrufen `GetActiveInternalFrames` von sollten Sie den `cInternalFrames` -Parameter auf 0 (null) und den- `ppInternalFrames` Parameter auf NULL festlegen.</span><span class="sxs-lookup"><span data-stu-id="0134a-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="0134a-123">`GetActiveInternalFrames`Enthält bei der ersten Rückgabe `pcInternalFrames` die Anzahl der internen Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="0134a-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="0134a-124">`GetActiveInternalFrames`sollte dann ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0134a-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="0134a-125">Sie sollten die richtige Anzahl ( `pcInternalFrames` ) im `cInternalFrames` -Parameter übergeben und einen Zeiger auf ein Array mit entsprechender Größenangabe in angeben `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="0134a-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="0134a-126">Verwenden Sie die [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) -Methode, um tatsächliche Stapel Rahmen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0134a-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0134a-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0134a-127">Requirements</span></span>  
 <span data-ttu-id="0134a-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0134a-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0134a-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0134a-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0134a-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0134a-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0134a-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0134a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0134a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0134a-132">See also</span></span>

- [<span data-ttu-id="0134a-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0134a-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0134a-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0134a-134">Debugging</span></span>](index.md)
