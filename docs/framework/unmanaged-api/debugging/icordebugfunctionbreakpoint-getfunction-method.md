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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1da93ea073d6ae9f2e79f251014b2db5282a22c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496013"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="e8d49-102">ICorDebugFunctionBreakpoint::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="e8d49-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="e8d49-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e8d49-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8d49-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8d49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8d49-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="e8d49-106">[out] Ein Zeiger auf die Adresse der Funktion, die in der der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e8d49-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d49-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8d49-107">Requirements</span></span>  
 <span data-ttu-id="e8d49-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8d49-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d49-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8d49-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8d49-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8d49-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8d49-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d49-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
