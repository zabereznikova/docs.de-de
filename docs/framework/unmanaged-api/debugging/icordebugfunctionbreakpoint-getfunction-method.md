---
title: ICorDebugFunctionBreakpoint::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 79a6c70399d5059d6959ac6127f22807138c00fa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213113"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="da64c-102">ICorDebugFunctionBreakpoint::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="da64c-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="da64c-103">Ruft einen Schnittstellen Zeiger auf eine icordebufunction ab, die auf die Funktion verweist, in der der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="da64c-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da64c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da64c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da64c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da64c-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="da64c-106">vorgenommen Ein Zeiger auf die Adresse der Funktion, in der der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="da64c-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da64c-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="da64c-107">Requirements</span></span>  
 <span data-ttu-id="da64c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da64c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da64c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da64c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da64c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da64c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da64c-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da64c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
