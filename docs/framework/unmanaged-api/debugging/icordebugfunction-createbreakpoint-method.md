---
title: ICorDebugFunction::CreateBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2881b1f420d8e177e093969b2cdd9f2ff36883f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412518"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="5956a-102">ICorDebugFunction::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="5956a-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="5956a-103">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="5956a-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5956a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5956a-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5956a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5956a-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="5956a-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFunctionBreakpoint-Objekts, das den neuen Haltepunkt für die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="5956a-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5956a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5956a-107">Requirements</span></span>  
 <span data-ttu-id="5956a-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5956a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5956a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5956a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5956a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5956a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5956a-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5956a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
