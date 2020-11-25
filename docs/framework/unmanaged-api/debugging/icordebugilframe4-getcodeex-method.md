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
ms.openlocfilehash: a88bb02626dc125c494e4bbe68bfe6ed8bfd3b7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719644"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="e0629-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="e0629-102">ICorDebugILFrame4::GetCodeEx Method</span></span>

<span data-ttu-id="e0629-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="e0629-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e0629-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0629-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0629-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0629-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0629-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0629-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="e0629-107">in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e0629-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="e0629-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0629-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0629-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0629-109">Remarks</span></span>  

 <span data-ttu-id="e0629-110">Diese Methode ähnelt der [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0629-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e0629-111">Das Aufrufen dieser Methode mit einem `flags` Wert von `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [GetCode](icordebugframe-getcode-method.md); wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e0629-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="e0629-112">`ILCODE_REJIT_IL` ermöglicht dem Debugger den Zugriff auf die von der ReJIT-Anforderung des Profilers definierte Il.</span><span class="sxs-lookup"><span data-stu-id="e0629-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e0629-113">Wenn die Il nicht instrumentiert ist, `ppCode` ist **null**, und die Methode gibt zurück `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="e0629-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0629-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e0629-114">Requirements</span></span>  

 <span data-ttu-id="e0629-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0629-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0629-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0629-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0629-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0629-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0629-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0629-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0629-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0629-119">See also</span></span>

- [<span data-ttu-id="e0629-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0629-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="e0629-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0629-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e0629-122">ReJIT: A How-To Guide</span><span class="sxs-lookup"><span data-stu-id="e0629-122">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
