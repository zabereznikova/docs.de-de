---
title: ICorDebugCode::CreateBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1173091a5f2d8814747c93f827150afe39b8b309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399111"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="075a1-102">ICorDebugCode::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="075a1-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="075a1-103">Erstellt einen Breakpoint in dieses Codesegment am angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="075a1-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="075a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="075a1-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="075a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="075a1-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="075a1-106">[in] Der Offset, bei der den Breakpoint erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="075a1-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="075a1-107">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugFunctionBreakpoint", das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="075a1-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="075a1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="075a1-108">Remarks</span></span>  
 <span data-ttu-id="075a1-109">Bevor der Haltepunkt aktiv ist, müssen sie das Prozessobjekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="075a1-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="075a1-110">Wenn dieser Code Microsoft intermediate Language (MSIL)-Code wird aus, und es eine just-in-Time (JIT gibt)-kompilierte, systemeigene Version des Codes, der Haltepunkt wird in der JIT-kompilierten Code als auch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="075a1-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="075a1-111">(Die gleiche ist true, wenn der Code JIT-kompilierten höher ist.)</span><span class="sxs-lookup"><span data-stu-id="075a1-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="075a1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="075a1-112">Requirements</span></span>  
 <span data-ttu-id="075a1-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="075a1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="075a1-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="075a1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="075a1-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="075a1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="075a1-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="075a1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075a1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="075a1-117">See Also</span></span>  
 
