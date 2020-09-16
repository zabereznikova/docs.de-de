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
ms.openlocfilehash: 06a0a4c788155d6fb909e4537b980f0ba740f21a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554813"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="f6b5b-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f6b5b-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="f6b5b-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f6b5b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f6b5b-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b5b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6b5b-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6b5b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6b5b-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="f6b5b-107">in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="f6b5b-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b5b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6b5b-109">Remarks</span></span>  
 <span data-ttu-id="f6b5b-110">Diese Methode ähnelt der [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f6b5b-111">Das Aufrufen dieser Methode mit einem `flags` Wert von `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="f6b5b-112">`ILCODE_REJIT_IL` ermöglicht dem Debugger den Zugriff auf die von der ReJIT-Anforderung des Profilers definierte Il.</span><span class="sxs-lookup"><span data-stu-id="f6b5b-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f6b5b-113">Wenn die Il nicht instrumentiert ist, `ppCode` ist **null**, und die Methode gibt zurück `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="f6b5b-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b5b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6b5b-114">Requirements</span></span>  
 <span data-ttu-id="f6b5b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6b5b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b5b-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6b5b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6b5b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6b5b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6b5b-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b5b-119">See also</span></span>

- [<span data-ttu-id="f6b5b-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b5b-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="f6b5b-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6b5b-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f6b5b-122">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="f6b5b-122">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
