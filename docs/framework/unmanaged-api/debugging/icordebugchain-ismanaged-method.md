---
title: ICorDebugChain::IsManaged-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a27ea95ca78f7db8f67ec2a13f02767e67619e97
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488057"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="f15ab-102">ICorDebugChain::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="f15ab-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="f15ab-103">Ruft einen Wert, der angibt, ob dieser Kette auf verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f15ab-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f15ab-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f15ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f15ab-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="f15ab-106">[out] `true` Wenn dieser Kette auf verwalteten Code ausgeführt wird, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f15ab-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f15ab-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f15ab-107">Requirements</span></span>  
 <span data-ttu-id="f15ab-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f15ab-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f15ab-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f15ab-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f15ab-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f15ab-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f15ab-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f15ab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
