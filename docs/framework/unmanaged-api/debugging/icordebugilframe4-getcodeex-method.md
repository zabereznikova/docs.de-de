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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb50459e36cfeb76a0c9a1e1cd4544260d484f45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926794"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="382bf-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="382bf-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="382bf-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="382bf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="382bf-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="382bf-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="382bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="382bf-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="382bf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="382bf-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="382bf-107">in Ein [ilcodekind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die von der ReJIT-Anforderung des Profilers definierte zwischen Sprache (IL) im Frame enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="382bf-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="382bf-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das den Code darstellt, der von diesem Stapel Rahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="382bf-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="382bf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="382bf-109">Remarks</span></span>  
 <span data-ttu-id="382bf-110">Diese Methode ähnelt der [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) -Methode, mit der Ausnahme, dass Sie optional auf Code zugreift, der von der ReJIT-Anforderung des Profilers definiert wird.</span><span class="sxs-lookup"><span data-stu-id="382bf-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="382bf-111">Das Aufrufen dieser Methode mit `flags` einem Wert `ILCODE_ORIGINAL_IL` von entspricht dem Aufrufen von [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); wenn die Methode instrumentiert ist, kann auf Ihre Il nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="382bf-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="382bf-112">`ILCODE_REJIT_IL`ermöglicht dem Debugger den Zugriff auf die von der ReJIT-Anforderung des Profilers definierte Il.</span><span class="sxs-lookup"><span data-stu-id="382bf-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="382bf-113">Wenn die Il nicht instrumentiert ist, `ppCode` ist **null**, und die Methode gibt `S_OK`zurück.</span><span class="sxs-lookup"><span data-stu-id="382bf-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="382bf-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="382bf-114">Requirements</span></span>  
 <span data-ttu-id="382bf-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="382bf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="382bf-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="382bf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="382bf-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="382bf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="382bf-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="382bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382bf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="382bf-119">See also</span></span>

- [<span data-ttu-id="382bf-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="382bf-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="382bf-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="382bf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="382bf-122">ReJIT Leitfaden</span><span class="sxs-lookup"><span data-stu-id="382bf-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
