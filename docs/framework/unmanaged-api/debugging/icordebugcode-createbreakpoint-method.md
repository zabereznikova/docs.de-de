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
ms.openlocfilehash: b02fb0a18bfbc2e93ec204706ca1f17dde5d8c8a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125713"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="bdf46-102">ICorDebugCode::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bdf46-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="bdf46-103">Erstellt in diesem Codesegment am angegebenen Offset einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="bdf46-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdf46-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdf46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bdf46-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="bdf46-106">in Der Offset, bei dem der Breakpoint erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdf46-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="bdf46-107">vorgenommen Ein Zeiger auf die Adresse eines icorentbugfunctionbreakpoint-Objekts, das den Breakpoint darstellt.</span><span class="sxs-lookup"><span data-stu-id="bdf46-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdf46-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdf46-108">Remarks</span></span>  
 <span data-ttu-id="bdf46-109">Bevor der Breakpoint aktiv ist, muss er dem Prozess Objekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bdf46-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="bdf46-110">Wenn dieser Code MSIL-Code (Microsoft Intermediate Language) ist und eine JIT (Just-in-Time)-kompilierte, systemeigene Version des Codes vorhanden ist, wird der Breakpoint ebenfalls im JIT-kompilierten Code angewendet.</span><span class="sxs-lookup"><span data-stu-id="bdf46-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="bdf46-111">(Das gleiche gilt, wenn der Code später JIT-kompiliert wird.)</span><span class="sxs-lookup"><span data-stu-id="bdf46-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf46-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdf46-112">Requirements</span></span>  
 <span data-ttu-id="bdf46-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf46-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdf46-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdf46-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdf46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdf46-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
