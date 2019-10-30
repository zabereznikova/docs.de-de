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
ms.openlocfilehash: 6f9d8cd79ac4107817d19fc0632aeaee287d253a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097011"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="27b56-102">ICorDebugModuleBreakpoint::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="27b56-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="27b56-103">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27b56-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27b56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27b56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27b56-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="27b56-106">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugModule`-Schnittstelle, die auf das Modul verweist, in dem der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27b56-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b56-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27b56-107">Requirements</span></span>  
 <span data-ttu-id="27b56-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b56-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b56-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27b56-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27b56-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27b56-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27b56-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b56-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b56-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27b56-112">See also</span></span>
