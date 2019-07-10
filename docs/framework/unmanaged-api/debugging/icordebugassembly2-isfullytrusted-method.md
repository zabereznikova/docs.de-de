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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744503"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="e3703-102">ICorDebugAssembly2::IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="e3703-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="e3703-103">Ruft einen Wert, der angibt, ob die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3703-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3703-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3703-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3703-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3703-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="e3703-106">[out] `true` Wenn die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem; erteilt wurde, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e3703-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3703-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3703-107">Remarks</span></span>  
 <span data-ttu-id="e3703-108">Diese Methode gibt, dass ein CORDBG_E_NOTREADY-HRESULT zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst, d. h., wenn kein Code in der Assembly wurde noch ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3703-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3703-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3703-109">Requirements</span></span>  
 <span data-ttu-id="e3703-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3703-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3703-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3703-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3703-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3703-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3703-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3703-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
