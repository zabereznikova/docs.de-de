---
title: ICorDebugAssembly2::IsFullyTrusted-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133949"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="6abad-102">ICorDebugAssembly2::IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="6abad-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="6abad-103">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="6abad-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6abad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6abad-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6abad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6abad-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="6abad-106">[out] `true`, wenn dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6abad-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6abad-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6abad-107">Remarks</span></span>  
 <span data-ttu-id="6abad-108">Diese Methode gibt ein HRESULT von CORDBG_E_NOTREADY zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst wurde, d. h., wenn noch kein Code in der Assembly ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6abad-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6abad-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6abad-109">Requirements</span></span>  
 <span data-ttu-id="6abad-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6abad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6abad-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6abad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6abad-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6abad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6abad-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6abad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
