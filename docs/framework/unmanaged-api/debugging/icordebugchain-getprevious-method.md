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
ms.openlocfilehash: 7fdcdf23dfee01e8bad1c95adb4de66f270d5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474968"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="a5581-102">ICorDebugChain::GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="a5581-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="a5581-103">Ruft die vorherige Kette von Frames für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="a5581-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5581-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5581-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5581-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5581-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="a5581-106">[out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die vorherige Kette von Frames für den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="a5581-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="a5581-107">Dieser Kette ist der erste Kette, `ppChain` ist null.</span><span class="sxs-lookup"><span data-stu-id="a5581-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5581-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5581-108">Requirements</span></span>  
 <span data-ttu-id="a5581-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5581-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5581-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5581-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5581-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5581-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5581-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5581-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
