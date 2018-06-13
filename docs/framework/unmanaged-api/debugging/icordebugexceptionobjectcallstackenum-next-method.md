---
title: ICorDebugExceptionObjectCallStackEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2216ad54c37bcaf62f3ddca6a4d48ef2cb4faf22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417426"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="49d6a-102">ICorDebugExceptionObjectCallStackEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="49d6a-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="49d6a-103">Ruft die angegebene Anzahl von [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen, die Informationen aus der Aufrufliste eines Ausnahmeobjekts enthalten.</span><span class="sxs-lookup"><span data-stu-id="49d6a-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49d6a-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49d6a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49d6a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="49d6a-106">[in] Die Anzahl der [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="49d6a-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="49d6a-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="49d6a-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="49d6a-108">[out] Ein Zeiger auf die Anzahl der [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49d6a-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d6a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49d6a-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d6a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49d6a-110">Requirements</span></span>  
 <span data-ttu-id="49d6a-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49d6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49d6a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49d6a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49d6a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49d6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49d6a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49d6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d6a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d6a-115">See Also</span></span>  
 [<span data-ttu-id="49d6a-116">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49d6a-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 [<span data-ttu-id="49d6a-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="49d6a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
