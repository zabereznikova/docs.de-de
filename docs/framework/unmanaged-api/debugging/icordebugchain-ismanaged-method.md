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
ms.openlocfilehash: 481f6d08e11a5f315c64b3d58df4ab291fa42e78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123849"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="f1f8c-102">ICorDebugChain::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="f1f8c-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="f1f8c-103">Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1f8c-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1f8c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1f8c-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="f1f8c-106">[out] `true`, wenn diese Kette verwalteten Code ausgeführt hat. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f1f8c-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f8c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1f8c-107">Requirements</span></span>  
 <span data-ttu-id="f1f8c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f8c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f8c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1f8c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1f8c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f8c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f8c-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f8c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
