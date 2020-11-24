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
ms.openlocfilehash: 17d5367564ec1ec98efc264ad9a5794c0d04a947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672135"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="0bcc2-102">ICorDebugExceptionObjectCallStackEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="0bcc2-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="0bcc2-103">Ruft die angegebene Anzahl von [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen ab, die Informationen aus der-Rückruf Stapel eines Ausnahme Objekts enthalten.</span><span class="sxs-lookup"><span data-stu-id="0bcc2-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bcc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bcc2-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bcc2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bcc2-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="0bcc2-106">in Die Anzahl der abzurufenden [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="0bcc2-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0bcc2-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="0bcc2-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0bcc2-108">vorgenommen Ein Zeiger auf die Anzahl der [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Instanzen, die tatsächlich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0bcc2-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bcc2-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0bcc2-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bcc2-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0bcc2-110">Requirements</span></span>  

 <span data-ttu-id="0bcc2-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bcc2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bcc2-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bcc2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bcc2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bcc2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bcc2-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bcc2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcc2-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bcc2-115">See also</span></span>

- [<span data-ttu-id="0bcc2-116">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bcc2-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="0bcc2-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0bcc2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
