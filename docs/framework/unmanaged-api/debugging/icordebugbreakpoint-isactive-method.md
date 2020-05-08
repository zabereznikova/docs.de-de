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
ms.openlocfilehash: 64a30ca85a75ebd11918ff630daffbb85c97f6dc
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894720"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="b8e0a-102">ICorDebugBreakpoint::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="b8e0a-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="b8e0a-103">Ruft einen Wert ab, der angibt `ICorDebugBreakpoint` , ob diese aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b8e0a-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e0a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8e0a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e0a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8e0a-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b8e0a-106">vorgenommen `true` , wenn dieser Haltepunkt aktiv ist. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b8e0a-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e0a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8e0a-107">Requirements</span></span>  
 <span data-ttu-id="b8e0a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e0a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e0a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8e0a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8e0a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8e0a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e0a-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e0a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
