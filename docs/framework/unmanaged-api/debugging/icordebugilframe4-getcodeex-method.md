---
title: ICorDebugILFrame4::GetCodeEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178783"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="e0435-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="e0435-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="e0435-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="e0435-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e0435-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0435-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0435-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0435-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0435-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0435-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="e0435-107">[in] Ein [ILCodeKind](ilcodekind-enumeration.md) ILCodeKind-Enumerationsmember, der angibt, ob die zwischengeschaltete Sprache (IL), die durch die ReJIT-Anforderung des Profilers definiert wird, im Frame enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e0435-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="e0435-108">[out] Ein Zeiger auf die Adresse eines "ICorDebugCode"-Objekts, das den Code darstellt, den dieser Stapelrahmen ausführt.</span><span class="sxs-lookup"><span data-stu-id="e0435-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0435-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0435-109">Remarks</span></span>  
 <span data-ttu-id="e0435-110">Diese Methode ähnelt der [ICorDebugFrame::GetCode-Methode,](icordebugframe-getcode-method.md) mit der Ausnahme, dass sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0435-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e0435-111">Aufrufen dieser Methode `flags` mit `ILCODE_ORIGINAL_IL` einem Wert von entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, ist auf ihre IL nicht zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="e0435-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="e0435-112">`ILCODE_REJIT_IL`ermöglicht dem Debugger den Zugriff auf die IL, die durch die ReJIT-Anforderung des Profilers definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0435-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e0435-113">Wenn die IL nicht `ppCode` instrumentiert ist, ist `S_OK` **null**, und die Methode gibt zurück.</span><span class="sxs-lookup"><span data-stu-id="e0435-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0435-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e0435-114">Requirements</span></span>  
 <span data-ttu-id="e0435-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0435-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0435-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0435-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0435-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0435-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0435-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0435-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0435-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0435-119">See also</span></span>

- [<span data-ttu-id="e0435-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0435-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="e0435-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0435-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e0435-122">ReJIT: Ein Anleitung</span><span class="sxs-lookup"><span data-stu-id="e0435-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
