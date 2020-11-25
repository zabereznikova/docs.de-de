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
ms.openlocfilehash: b6363ef901d5297862ca46e685bb783aaaeb4123
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709621"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="eb50e-102">ICorDebugModuleBreakpoint::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="eb50e-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="eb50e-103">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eb50e-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb50e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb50e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb50e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb50e-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="eb50e-106">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugModule` Schnittstelle, die auf das Modul verweist, in dem der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eb50e-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb50e-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eb50e-107">Requirements</span></span>  

 <span data-ttu-id="eb50e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb50e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb50e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb50e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb50e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb50e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb50e-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb50e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb50e-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb50e-112">See also</span></span>
