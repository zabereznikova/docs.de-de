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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e264f2361c739536d15fbf31d366db74e107bac2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085102"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="a596b-102">ICorDebugThread3::GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="a596b-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="a596b-103">Gibt ein Array von internen Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekte) auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="a596b-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a596b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a596b-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a596b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a596b-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="a596b-106">[in] Die Anzahl der erwarteten internen Frames `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="a596b-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="a596b-107">[out] Ein Zeiger auf eine `ULONG32` , enthält die Anzahl der internen Frames im Stapel.</span><span class="sxs-lookup"><span data-stu-id="a596b-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="a596b-108">[in, out] Ein Zeiger auf die Adresse eines Arrays von internen Frames im Stapel.</span><span class="sxs-lookup"><span data-stu-id="a596b-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a596b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a596b-109">Return Value</span></span>  
 <span data-ttu-id="a596b-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a596b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a596b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a596b-111">HRESULT</span></span>|<span data-ttu-id="a596b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a596b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a596b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a596b-113">S_OK</span></span>|<span data-ttu-id="a596b-114">Die [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="a596b-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="a596b-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a596b-115">E_INVALIDARG</span></span>|`cInternalFrames` <span data-ttu-id="a596b-116">ist nicht 0 (null) und `ppInternalFrames` ist `null`, oder `pcInternalFrames` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="a596b-116">is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="a596b-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="a596b-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|`ppInternalFrames` <span data-ttu-id="a596b-118">ist kleiner als die Anzahl der internen Frames.</span><span class="sxs-lookup"><span data-stu-id="a596b-118">is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a596b-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a596b-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a596b-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a596b-120">Remarks</span></span>  
 <span data-ttu-id="a596b-121">Interner Frames sind Datenstrukturen, die von der Laufzeit zum Speichern von temporären Daten auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="a596b-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="a596b-122">Beim ersten Aufruf `GetActiveInternalFrames`, legen Sie die `cInternalFrames` Parameter auf 0 (null), und die `ppInternalFrames` Parameter auf null.</span><span class="sxs-lookup"><span data-stu-id="a596b-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="a596b-123">Wenn `GetActiveInternalFrames` zuerst zurückgegeben wird, `pcInternalFrames` enthält die Anzahl der internen Frames im Stapel.</span><span class="sxs-lookup"><span data-stu-id="a596b-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 `GetActiveInternalFrames` <span data-ttu-id="a596b-124">Anschließend sollte ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a596b-124">should then be called a second time.</span></span> <span data-ttu-id="a596b-125">Übergeben Sie die richtige Anzahl (`pcInternalFrames`) in der `cInternalFrames` -Parameter, und geben Sie einen Zeiger auf ein Array, in geeigneter Größe `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="a596b-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="a596b-126">Verwenden der [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Stapelrahmen der Methode, um tatsächliche zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a596b-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a596b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a596b-127">Requirements</span></span>  
 <span data-ttu-id="a596b-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a596b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a596b-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a596b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a596b-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a596b-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a596b-131">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a596b-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a596b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a596b-132">See also</span></span>

- [<span data-ttu-id="a596b-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a596b-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a596b-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a596b-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
