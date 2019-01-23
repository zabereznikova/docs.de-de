---
title: ICorDebugModuleBreakpoint::GetModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53137021fe9ccaf170bed28918b8f5fe87715b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504990"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="065ab-102">ICorDebugModuleBreakpoint::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="065ab-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="065ab-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugModule", die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="065ab-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="065ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="065ab-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="065ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="065ab-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="065ab-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugModule` -Schnittstelle, die das Modul verweist, in dem der Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="065ab-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="065ab-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="065ab-107">Requirements</span></span>  
 <span data-ttu-id="065ab-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="065ab-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="065ab-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="065ab-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="065ab-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="065ab-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="065ab-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="065ab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065ab-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="065ab-112">See also</span></span>

