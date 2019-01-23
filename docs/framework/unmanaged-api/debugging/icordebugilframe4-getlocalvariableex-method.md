---
title: ICorDebugILFrame4::GetLocalVariableEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18a6154ad3fe3ee384a38007ab371e83482193ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545974"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="d1b8e-102">ICorDebugILFrame4::GetLocalVariableEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d1b8e-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="d1b8e-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="d1b8e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d1b8e-104">Ruft den Wert einer spezifizierten lokalen Variable in deren Intermediate Language (IL)-Stapelrahmen ab, und greift optional auf eine Variable zu, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b8e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1b8e-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1b8e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1b8e-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="d1b8e-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob eine Variable in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde, im Rahmen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="d1b8e-108">[in] Der Index der lokalen Variable im IL-Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d1b8e-109">[out] Ein Zeiger auf die Adresse ein "ICorDebugValue"-Objekt, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1b8e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1b8e-110">Remarks</span></span>  
 <span data-ttu-id="d1b8e-111">Diese Methode ähnelt der [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) -Methode, mit dem Unterschied, dass sie optional eine Variable, die in der Profiler-ReJIT-Instrumentierung hinzugefügt zugreift.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="d1b8e-112">Beim Aufruf dieser Methode eine `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist dieser Variablen können nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="d1b8e-113">`ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen in der Profiler-ReJIT-Instrumentierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="d1b8e-114">Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.</span><span class="sxs-lookup"><span data-stu-id="d1b8e-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b8e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1b8e-115">Requirements</span></span>  
 <span data-ttu-id="d1b8e-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1b8e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b8e-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1b8e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1b8e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1b8e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1b8e-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b8e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b8e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1b8e-120">See also</span></span>
- [<span data-ttu-id="d1b8e-121">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1b8e-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="d1b8e-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1b8e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d1b8e-123">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="d1b8e-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
