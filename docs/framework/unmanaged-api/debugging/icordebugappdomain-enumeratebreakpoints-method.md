---
title: ICorDebugAppDomain::EnumerateBreakpoints-Methode
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
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2363b3159bef4453eb3eeb910d3d304806c56e6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="457fb-102">ICorDebugAppDomain::EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="457fb-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="457fb-103">Ruft einen Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="457fb-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="457fb-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="457fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="457fb-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="457fb-106">[out] Ein Zeiger auf die Adresse eines ICorDebugBreakpointEnum-Objekts, das den Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="457fb-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="457fb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="457fb-107">Remarks</span></span>  
 <span data-ttu-id="457fb-108">Der Enumerator schließt alle Typen von Haltepunkten, einschließlich funktionshaltepunkten und Datenhaltepunkte.</span><span class="sxs-lookup"><span data-stu-id="457fb-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457fb-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="457fb-109">Requirements</span></span>  
 <span data-ttu-id="457fb-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="457fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457fb-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="457fb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="457fb-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="457fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="457fb-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
