---
title: ICorDebugILFrame4::GetCodeEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5d1d480014e90d3fea9790b10e0dace5a0847ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="53290-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="53290-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="53290-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="53290-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="53290-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53290-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53290-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="53290-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53290-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="53290-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="53290-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) Enumerationsmember, der angibt, ob die intermediate Language (IL), die durch die Profiler-ReJIT-Anfrage definiert, die im Rahmen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="53290-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="53290-108">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugCode", das den Code darstellt, den diesem Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53290-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53290-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53290-109">Remarks</span></span>  
 <span data-ttu-id="53290-110">Diese Methode ähnelt der [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) -Methode, mit dem Unterschied, dass sie optional durch den Profiler-ReJIT-Anfrage definiert Code zugreift.</span><span class="sxs-lookup"><span data-stu-id="53290-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="53290-111">Beim Aufrufen dieser Methode mit einem `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, die IL nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="53290-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="53290-112">`ILCODE_REJIT_IL`kann der Debugger den IL-Code durch den Profiler-ReJIT-Anfrage definiert den Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="53290-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="53290-113">Wenn die IL nicht instrumentiert, `ppCode` ist **null**, und die Methode gibt `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="53290-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53290-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53290-114">Requirements</span></span>  
 <span data-ttu-id="53290-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53290-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53290-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53290-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53290-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53290-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53290-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53290-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53290-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53290-119">See Also</span></span>  
 [<span data-ttu-id="53290-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53290-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="53290-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53290-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="53290-122">ReJIT: Eine Anleitung</span><span class="sxs-lookup"><span data-stu-id="53290-122">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
