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
ms.openlocfilehash: dd82709064fe7f7d912d93f4b3f0248769f02b9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894885"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="385a9-102">ICorDebugAssembly2::IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="385a9-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="385a9-103">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="385a9-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="385a9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="385a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="385a9-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="385a9-106">vorgenommen `true` , wenn der Assembly vom Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit gewährt wurde. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="385a9-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="385a9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="385a9-107">Remarks</span></span>  
 <span data-ttu-id="385a9-108">Diese Methode gibt ein HRESULT von CORDBG_E_NOTREADY zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst wurde, d. h., wenn noch kein Code in der Assembly ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="385a9-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385a9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="385a9-109">Requirements</span></span>  
 <span data-ttu-id="385a9-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="385a9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="385a9-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="385a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="385a9-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="385a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="385a9-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="385a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
