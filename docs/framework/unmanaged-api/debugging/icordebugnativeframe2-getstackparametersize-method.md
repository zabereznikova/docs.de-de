---
title: ICorDebugNativeFrame2::GetStackParameterSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47968d7550c3d16d201680caab705c0d7c85c784
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994577"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="0abf5-102">ICorDebugNativeFrame2::GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="0abf5-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="0abf5-103">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="0abf5-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0abf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0abf5-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="0abf5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0abf5-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="0abf5-106">[out] Ein Zeiger auf die kumulierte Größe der Parameter im Stapel.</span><span class="sxs-lookup"><span data-stu-id="0abf5-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0abf5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0abf5-107">Return Value</span></span>  
 <span data-ttu-id="0abf5-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0abf5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0abf5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0abf5-109">HRESULT</span></span>|<span data-ttu-id="0abf5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0abf5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0abf5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0abf5-111">S_OK</span></span>|<span data-ttu-id="0abf5-112">Die Größe des Stapels wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0abf5-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="0abf5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0abf5-113">S_FALSE</span></span>|<span data-ttu-id="0abf5-114">`GetStackParameterSize` wurde eine nicht-X86 Plattform aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0abf5-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="0abf5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0abf5-115">E_FAIL</span></span>|<span data-ttu-id="0abf5-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="0abf5-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="0abf5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0abf5-117">E_INVALIDARG</span></span>|<span data-ttu-id="0abf5-118">`pSize` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0abf5-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0abf5-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0abf5-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0abf5-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0abf5-120">Remarks</span></span>  
 <span data-ttu-id="0abf5-121">Die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Methoden passen sich nicht auf den Stapelzeiger für Parameter, die auf dem Stapel abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0abf5-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="0abf5-122">Sie können stattdessen den Rückgabewert von `GetStackParameterSize` anpassen den Stapelzeiger als Ausgangswert für eine native Entlader, die für die Parameter angepasst.</span><span class="sxs-lookup"><span data-stu-id="0abf5-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0abf5-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0abf5-123">Requirements</span></span>  
 <span data-ttu-id="0abf5-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0abf5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0abf5-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0abf5-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0abf5-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0abf5-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0abf5-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0abf5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abf5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0abf5-128">See also</span></span>

- [<span data-ttu-id="0abf5-129">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0abf5-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="0abf5-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0abf5-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0abf5-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0abf5-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
