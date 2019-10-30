---
title: ICorDebugChain::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: b964d58bddb174da38fc8988ec807fd3129b5fcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123826"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="820de-102">ICorDebugChain::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="820de-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="820de-103">Ruft den physischen Thread ab, zu dem diese rufkette gehört.</span><span class="sxs-lookup"><span data-stu-id="820de-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="820de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="820de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="820de-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="820de-106">vorgenommen Ein Zeiger auf ein ICorDebugThread-Objekt, das den physischen Thread darstellt, zu dem diese rufkette gehört.</span><span class="sxs-lookup"><span data-stu-id="820de-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="820de-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="820de-107">Requirements</span></span>  
 <span data-ttu-id="820de-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="820de-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="820de-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="820de-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="820de-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="820de-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="820de-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="820de-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
