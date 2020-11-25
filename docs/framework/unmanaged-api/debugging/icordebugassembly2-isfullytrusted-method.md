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
ms.openlocfilehash: 8a2a6be0db76f5ee2c7fa67c2038e0a5c845bd0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719709"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="84baa-102">ICorDebugAssembly2::IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="84baa-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>

<span data-ttu-id="84baa-103">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="84baa-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84baa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84baa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84baa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84baa-105">Parameters</span></span>  

 `pbFullyTrusted`  
 <span data-ttu-id="84baa-106">[out] `true` , wenn der Assembly vom Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit gewährt wurde. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="84baa-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84baa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84baa-107">Remarks</span></span>  

 <span data-ttu-id="84baa-108">Diese Methode gibt ein HRESULT von CORDBG_E_NOTREADY zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst wurde, d. h., wenn noch kein Code in der Assembly ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="84baa-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84baa-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84baa-109">Requirements</span></span>  

 <span data-ttu-id="84baa-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84baa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84baa-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84baa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84baa-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84baa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84baa-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84baa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
