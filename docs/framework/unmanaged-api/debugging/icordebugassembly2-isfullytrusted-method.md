---
title: ICorDebugAssembly2::IsFullyTrusted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly2.IsFullyTrusted
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19058308876f80afdbaec73583242aa8ad3c33cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="6d50c-102">ICorDebugAssembly2::IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="6d50c-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="6d50c-103">Ruft einen Wert, der angibt, ob die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d50c-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d50c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d50c-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d50c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d50c-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="6d50c-106">[out] `true` Wenn die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem; erteilt wurde, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6d50c-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d50c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d50c-107">Remarks</span></span>  
 <span data-ttu-id="6d50c-108">Diese Methode gibt, dass ein CORDBG_E_NOTREADY-HRESULT zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst, d. h., wenn kein Code in der Assembly wurde noch ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d50c-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d50c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d50c-109">Requirements</span></span>  
 <span data-ttu-id="6d50c-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d50c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d50c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d50c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d50c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d50c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d50c-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d50c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
