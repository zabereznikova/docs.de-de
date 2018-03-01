---
title: ICorDebugFunctionBreakpoint::GetFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b9e59c26053d2eec534ca1cd56cf0ed277f87fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="6976e-102">ICorDebugFunctionBreakpoint::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="6976e-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="6976e-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="6976e-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6976e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6976e-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6976e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6976e-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="6976e-106">[out] Ein Zeiger auf die Adresse der Funktion in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="6976e-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6976e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6976e-107">Requirements</span></span>  
 <span data-ttu-id="6976e-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6976e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6976e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6976e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6976e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6976e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6976e-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6976e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
