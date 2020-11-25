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
ms.openlocfilehash: cfe884c3d26e7a52618eb9945f0af9a167132f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724376"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="5503f-102">ICorDebugChain::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="5503f-102">ICorDebugChain::IsManaged Method</span></span>

<span data-ttu-id="5503f-103">Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5503f-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5503f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5503f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5503f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5503f-105">Parameters</span></span>  

 `pManaged`  
 <span data-ttu-id="5503f-106">[out] `true` , wenn diese Kette verwalteten Code ausführen kann. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="5503f-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5503f-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5503f-107">Requirements</span></span>  

 <span data-ttu-id="5503f-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5503f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5503f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5503f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5503f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5503f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5503f-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5503f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
