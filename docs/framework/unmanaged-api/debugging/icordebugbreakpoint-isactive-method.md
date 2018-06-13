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
ms.openlocfilehash: 61aece9dd506d6e4af8718e45cc772d120a7d579
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401660"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="94714-102">ICorDebugBreakpoint::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="94714-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="94714-103">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="94714-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94714-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94714-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94714-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94714-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="94714-106">[out] `true` ist dieser Haltepunkt aktiv ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="94714-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94714-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94714-107">Requirements</span></span>  
 <span data-ttu-id="94714-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94714-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94714-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94714-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94714-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94714-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94714-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94714-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
