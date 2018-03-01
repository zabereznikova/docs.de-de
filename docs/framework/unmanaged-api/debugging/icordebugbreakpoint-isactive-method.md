---
title: ICorDebugBreakpoint::IsActive-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 394caaaff0b0269acd63a590225ffde420ebfd2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="c452e-102">ICorDebugBreakpoint::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="c452e-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="c452e-103">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c452e-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c452e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c452e-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c452e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c452e-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="c452e-106">[out] `true` ist dieser Haltepunkt aktiv ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c452e-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c452e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c452e-107">Requirements</span></span>  
 <span data-ttu-id="c452e-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c452e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c452e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c452e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c452e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c452e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c452e-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c452e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
