---
title: ICorDebugNativeFrame2::GetStackParameterSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="bacbb-102">ICorDebugNativeFrame2::GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bacbb-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="bacbb-103">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="bacbb-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacbb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bacbb-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bacbb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bacbb-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="bacbb-106">[out] Ein Zeiger auf die kumulierte Größe der Parameter auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="bacbb-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bacbb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bacbb-107">Return Value</span></span>  
 <span data-ttu-id="bacbb-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bacbb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bacbb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bacbb-109">HRESULT</span></span>|<span data-ttu-id="bacbb-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bacbb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bacbb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bacbb-111">S_OK</span></span>|<span data-ttu-id="bacbb-112">Die Größe des Stapels wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bacbb-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="bacbb-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bacbb-113">S_FALSE</span></span>|<span data-ttu-id="bacbb-114">`GetStackParameterSize`auf einer Plattform nicht X86 aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="bacbb-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="bacbb-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bacbb-115">E_FAIL</span></span>|<span data-ttu-id="bacbb-116">`The size of the parameters could not be returned`</span><span class="sxs-lookup"><span data-stu-id="bacbb-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="bacbb-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bacbb-117">E_INVALIDARG</span></span>|<span data-ttu-id="bacbb-118">`pSize`Ist `null`.</span><span class="sxs-lookup"><span data-stu-id="bacbb-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="bacbb-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="bacbb-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bacbb-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bacbb-120">Remarks</span></span>  
 <span data-ttu-id="bacbb-121">Die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Methoden passen sich nicht auf den Stapelzeiger für Parameter, die auf dem Stapel abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bacbb-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="bacbb-122">Stattdessen können Sie den Rückgabewert von `GetStackParameterSize` zum Anpassen des Stapelzeiger Ausgangswert für einen systemeigenen Entlader festzulegen, die für die Parameter angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="bacbb-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacbb-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bacbb-123">Requirements</span></span>  
 <span data-ttu-id="bacbb-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bacbb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacbb-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bacbb-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bacbb-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bacbb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bacbb-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacbb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacbb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bacbb-128">See Also</span></span>  
 [<span data-ttu-id="bacbb-129">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacbb-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="bacbb-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bacbb-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bacbb-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bacbb-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
