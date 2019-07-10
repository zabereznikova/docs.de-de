---
title: ICorDebugChain::GetPrevious-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c795c2fbbfdc45b6e1aac6684f730f55fc106a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746417"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="bb914-102">ICorDebugChain::GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="bb914-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="bb914-103">Ruft die vorherige Kette von Frames für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="bb914-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb914-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb914-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb914-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb914-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="bb914-106">[out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die vorherige Kette von Frames für den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb914-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="bb914-107">Dieser Kette ist der erste Kette, `ppChain` ist null.</span><span class="sxs-lookup"><span data-stu-id="bb914-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb914-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb914-108">Requirements</span></span>  
 <span data-ttu-id="bb914-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb914-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb914-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb914-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb914-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb914-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb914-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb914-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
