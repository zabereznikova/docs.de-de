---
title: ICorDebugBreakpoint::IsActive-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df5bed730211676acc4770c91cc6551bde0179b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645330"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="c36c0-102">ICorDebugBreakpoint::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="c36c0-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="c36c0-103">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c36c0-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c36c0-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c36c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c36c0-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="c36c0-106">[out] `true` ist dieser Haltepunkt aktiv ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c36c0-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36c0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c36c0-107">Requirements</span></span>  
 <span data-ttu-id="c36c0-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c36c0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c36c0-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c36c0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c36c0-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c36c0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c36c0-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c36c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
