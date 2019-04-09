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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200141"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="c4a6d-102">ICorDebugNativeFrame2::GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="c4a6d-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="c4a6d-103">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4a6d-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4a6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4a6d-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="c4a6d-106">[out] Ein Zeiger auf die kumulierte Größe der Parameter im Stapel.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4a6d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4a6d-107">Return Value</span></span>  
 <span data-ttu-id="c4a6d-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c4a6d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4a6d-109">HRESULT</span></span>|<span data-ttu-id="c4a6d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4a6d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4a6d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4a6d-111">S_OK</span></span>|<span data-ttu-id="c4a6d-112">Die Größe des Stapels wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="c4a6d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c4a6d-113">S_FALSE</span></span>|`GetStackParameterSize` <span data-ttu-id="c4a6d-114">wurde eine nicht-X86 Plattform aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-114">was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="c4a6d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4a6d-115">E_FAIL</span></span>|`The size of the parameters could not be returned`<span data-ttu-id="c4a6d-116">sein.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-116">.</span></span>|  
|<span data-ttu-id="c4a6d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c4a6d-117">E_INVALIDARG</span></span>|`pSize` <span data-ttu-id="c4a6d-118">ist `null`.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-118">Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c4a6d-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4a6d-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4a6d-120">Remarks</span></span>  
 <span data-ttu-id="c4a6d-121">Die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Methoden passen sich nicht auf den Stapelzeiger für Parameter, die auf dem Stapel abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="c4a6d-122">Sie können stattdessen den Rückgabewert von `GetStackParameterSize` anpassen den Stapelzeiger als Ausgangswert für eine native Entlader, die für die Parameter angepasst.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4a6d-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-123">Requirements</span></span>  
 <span data-ttu-id="c4a6d-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4a6d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4a6d-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4a6d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4a6d-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4a6d-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c4a6d-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c4a6d-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4a6d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4a6d-128">See also</span></span>

- [<span data-ttu-id="c4a6d-129">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4a6d-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="c4a6d-130">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c4a6d-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
