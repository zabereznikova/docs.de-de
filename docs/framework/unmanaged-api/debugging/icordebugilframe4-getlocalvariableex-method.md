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
ms.openlocfilehash: c6594bb72ce9cd2fbfa9cdafebc152a90618b810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193082"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="47d38-102">ICorDebugILFrame4::GetLocalVariableEx-Methode</span><span class="sxs-lookup"><span data-stu-id="47d38-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="47d38-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="47d38-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="47d38-104">Ruft den Wert einer spezifizierten lokalen Variable in deren Intermediate Language (IL)-Stapelrahmen ab, und greift optional auf eine Variable zu, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="47d38-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d38-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47d38-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47d38-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47d38-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="47d38-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob eine Variable in der Profiler-ReJIT-Instrumentierung hinzugefügt wurde, im Rahmen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="47d38-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="47d38-108">[in] Der Index der lokalen Variable im IL-Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="47d38-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="47d38-109">[out] Ein Zeiger auf die Adresse ein "ICorDebugValue"-Objekt, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="47d38-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d38-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47d38-110">Remarks</span></span>  
 <span data-ttu-id="47d38-111">Diese Methode ähnelt der [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) -Methode, mit dem Unterschied, dass sie optional eine Variable, die in der Profiler-ReJIT-Instrumentierung hinzugefügt zugreift.</span><span class="sxs-lookup"><span data-stu-id="47d38-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="47d38-112">Beim Aufruf dieser Methode eine `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Wenn die Methode mit zusätzlichen lokalen Variablen instrumentiert ist dieser Variablen können nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="47d38-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> `ILCODE_REJIT_IL` <span data-ttu-id="47d38-113">ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="47d38-113">allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="47d38-114">Ist die IL nicht instrumentiert, gibt die Methode `E_INVALIDARG` zurück.</span><span class="sxs-lookup"><span data-stu-id="47d38-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d38-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47d38-115">Requirements</span></span>  
 <span data-ttu-id="47d38-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47d38-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d38-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47d38-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47d38-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47d38-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="47d38-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="47d38-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47d38-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47d38-120">See also</span></span>

- [<span data-ttu-id="47d38-121">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47d38-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="47d38-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="47d38-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="47d38-123">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="47d38-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
