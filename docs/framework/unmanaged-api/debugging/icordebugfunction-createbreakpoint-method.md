---
title: ICorDebugFunction::CreateBreakpoint-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0565f7ad5e57ad63607b1a28e3ecb26965afd974
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="cc482-102">ICorDebugFunction::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="cc482-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="cc482-103">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc482-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc482-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc482-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc482-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc482-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="cc482-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFunctionBreakpoint-Objekts, das den neuen Haltepunkt für die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="cc482-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc482-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cc482-107">Requirements</span></span>  
 <span data-ttu-id="cc482-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc482-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc482-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc482-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc482-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc482-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc482-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc482-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
