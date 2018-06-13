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
ms.openlocfilehash: 76ff2e502859bff27ee29a280e0d247ca1bbf1e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419555"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="4ac3a-102">ICorDebugNativeFrame2::GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="4ac3a-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="4ac3a-103">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ac3a-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ac3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ac3a-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="4ac3a-106">[out] Ein Zeiger auf die kumulierte Größe der Parameter auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ac3a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ac3a-107">Return Value</span></span>  
 <span data-ttu-id="4ac3a-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4ac3a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ac3a-109">HRESULT</span></span>|<span data-ttu-id="4ac3a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ac3a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ac3a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ac3a-111">S_OK</span></span>|<span data-ttu-id="4ac3a-112">Die Größe des Stapels wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="4ac3a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4ac3a-113">S_FALSE</span></span>|<span data-ttu-id="4ac3a-114">`GetStackParameterSize` auf einer Plattform nicht X86 aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="4ac3a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ac3a-115">E_FAIL</span></span>|<span data-ttu-id="4ac3a-116">`The size of the parameters could not be returned`</span><span class="sxs-lookup"><span data-stu-id="4ac3a-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="4ac3a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ac3a-117">E_INVALIDARG</span></span>|<span data-ttu-id="4ac3a-118">`pSize` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4ac3a-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="4ac3a-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ac3a-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ac3a-120">Remarks</span></span>  
 <span data-ttu-id="4ac3a-121">Die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Methoden passen sich nicht auf den Stapelzeiger für Parameter, die auf dem Stapel abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="4ac3a-122">Stattdessen können Sie den Rückgabewert von `GetStackParameterSize` zum Anpassen des Stapelzeiger Ausgangswert für einen systemeigenen Entlader festzulegen, die für die Parameter angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="4ac3a-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac3a-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ac3a-123">Requirements</span></span>  
 <span data-ttu-id="4ac3a-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ac3a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac3a-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ac3a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ac3a-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ac3a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ac3a-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac3a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac3a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ac3a-128">See Also</span></span>  
 [<span data-ttu-id="4ac3a-129">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ac3a-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="4ac3a-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4ac3a-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ac3a-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4ac3a-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
