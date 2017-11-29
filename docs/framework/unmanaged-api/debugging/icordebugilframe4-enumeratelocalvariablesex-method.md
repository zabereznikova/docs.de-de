---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4551bf387c43ed6cbb2c6a37bba5ec1ec768e210
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="03468-102">ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode</span><span class="sxs-lookup"><span data-stu-id="03468-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="03468-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="03468-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="03468-104">Ruft einen Enumerator für die lokale Variable im Rahmen ab, und schließt optional Variablen ein, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="03468-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03468-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03468-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03468-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="03468-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="03468-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) Enumerationsmember, der angibt, ob die Variablen in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, im Rahmen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="03468-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="03468-108">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValueEnum", das den Enumerator für die lokalen Variablen in diesem Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="03468-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03468-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03468-109">Remarks</span></span>  
 <span data-ttu-id="03468-110">Diese Methode ähnelt der [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) -Methode, mit dem Unterschied, dass sie optional auf Variablen in der Profiler-ReJIT-Instrumentierung hinzugefügt zugreift.</span><span class="sxs-lookup"><span data-stu-id="03468-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="03468-111">Festlegen von `flags` auf `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [ICorDebugILFrame:: EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="03468-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="03468-112">Die Einstellung von `flags` auf `ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="03468-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="03468-113">Ist die Intermediate Language (IL) nicht instrumentiert, ist die Enumeration leer und die Methode gibt `S_OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="03468-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="03468-114">Der Enumerator schließt möglicherweise nicht alle lokalen Variablen in die ausgeführte Methode ein, da einige von ihnen möglicherweise nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="03468-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03468-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03468-115">Requirements</span></span>  
 <span data-ttu-id="03468-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03468-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03468-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03468-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03468-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03468-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03468-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03468-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03468-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03468-120">See Also</span></span>  
 [<span data-ttu-id="03468-121">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03468-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="03468-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="03468-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="03468-123">ReJIT: Eine Anleitung</span><span class="sxs-lookup"><span data-stu-id="03468-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
