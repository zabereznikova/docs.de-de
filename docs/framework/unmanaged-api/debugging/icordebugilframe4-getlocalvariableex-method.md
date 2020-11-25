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
ms.openlocfilehash: c9dfbdc141c19cb9bee87a34d838c5e7c6b366df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724961"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="05020-102">ICorDebugILFrame4::GetLocalVariableEx-Methode</span><span class="sxs-lookup"><span data-stu-id="05020-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>

<span data-ttu-id="05020-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="05020-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="05020-104">Ruft den Wert einer spezifizierten lokalen Variable in deren Intermediate Language (IL)-Stapelrahmen ab, und greift optional auf eine Variable zu, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="05020-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05020-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05020-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05020-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="05020-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="05020-107">in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob eine in der Profiler-ReJIT-Instrumentation hinzugefügte Variable im Frame enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="05020-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="05020-108">[in] Der Index der lokalen Variable im IL-Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="05020-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="05020-109">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="05020-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05020-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05020-110">Remarks</span></span>  

 <span data-ttu-id="05020-111">Diese Methode ähnelt der [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) -Methode, außer dass Sie optional auf eine Variable zugreift, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="05020-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="05020-112">Das Aufrufen dieser Methode mit einem `flags` Wert von `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetLocalVariable](icordebugilframe-getlocalvariable-method.md). wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist, kann auf diese Variablen nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="05020-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="05020-113">`ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="05020-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="05020-114">Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.</span><span class="sxs-lookup"><span data-stu-id="05020-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05020-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05020-115">Requirements</span></span>  

 <span data-ttu-id="05020-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05020-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05020-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05020-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05020-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05020-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05020-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05020-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05020-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05020-120">See also</span></span>

- [<span data-ttu-id="05020-121">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05020-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="05020-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="05020-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="05020-123">ReJIT: A How-To Guide</span><span class="sxs-lookup"><span data-stu-id="05020-123">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
