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
ms.openlocfilehash: ca742ba9e89e1d189cfa38dead314df0d8b4e9d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792765"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="bfdc1-102">ICorDebugNativeFrame2::GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bfdc1-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="bfdc1-103">Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfdc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfdc1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bfdc1-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="bfdc1-106">vorgenommen Ein Zeiger auf die kumulierte Größe der Parameter im Stapel.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfdc1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bfdc1-107">Return Value</span></span>  
 <span data-ttu-id="bfdc1-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bfdc1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfdc1-109">HRESULT</span></span>|<span data-ttu-id="bfdc1-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfdc1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfdc1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfdc1-111">S_OK</span></span>|<span data-ttu-id="bfdc1-112">Die Stapelgröße wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="bfdc1-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bfdc1-113">S_FALSE</span></span>|<span data-ttu-id="bfdc1-114">`GetStackParameterSize` wurde auf einer nicht-x86-Plattform aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="bfdc1-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfdc1-115">E_FAIL</span></span>|<span data-ttu-id="bfdc1-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="bfdc1-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bfdc1-117">E_INVALIDARG</span></span>|<span data-ttu-id="bfdc1-118">`pSize` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="bfdc1-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="bfdc1-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfdc1-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfdc1-120">Remarks</span></span>  
 <span data-ttu-id="bfdc1-121">Die [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Methoden passen den Stapelzeiger nicht für Parameter an, die auf dem Stapel abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="bfdc1-122">Stattdessen können Sie den von `GetStackParameterSize` zurückgegebenen Wert verwenden, um den Stapelzeiger auf einen Ausgangswert für einen nativen Unwinder festzulegen, der für die Parameter angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="bfdc1-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfdc1-123">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bfdc1-123">Requirements</span></span>  
 <span data-ttu-id="bfdc1-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfdc1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfdc1-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfdc1-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfdc1-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfdc1-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfdc1-127">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfdc1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdc1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfdc1-128">See also</span></span>

- [<span data-ttu-id="bfdc1-129">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfdc1-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="bfdc1-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bfdc1-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="bfdc1-131">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bfdc1-131">Debugging</span></span>](index.md)
