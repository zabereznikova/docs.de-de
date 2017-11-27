---
title: ICorDebugModuleBreakpoint::GetModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: afdd16cbdb2b33ad0806fbce1dab5e6d7130fb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="5c48a-102">ICorDebugModuleBreakpoint::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="5c48a-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="5c48a-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugModule", die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5c48a-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c48a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c48a-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c48a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c48a-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="5c48a-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugModule` Schnittstelle, die das Modul verweist, in denen der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="5c48a-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c48a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c48a-107">Requirements</span></span>  
 <span data-ttu-id="5c48a-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c48a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c48a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c48a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c48a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c48a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c48a-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c48a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c48a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c48a-112">See Also</span></span>  
 
