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
ms.openlocfilehash: da22570441324a01fea307116bc23601e62919a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411363"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="4d52e-102">ICorDebugFunctionBreakpoint::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="4d52e-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="4d52e-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d52e-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d52e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d52e-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d52e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d52e-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="4d52e-106">[out] Ein Zeiger auf die Adresse der Funktion in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d52e-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d52e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d52e-107">Requirements</span></span>  
 <span data-ttu-id="4d52e-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d52e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d52e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d52e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d52e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d52e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d52e-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d52e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
