---
title: ICorDebugFrame::GetChain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c020b9f6c074be11e3433939ce6898586123cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412606"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="8b8df-102">ICorDebugFrame::GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="8b8df-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="8b8df-103">Ruft einen Zeiger auf die Kette dieses Rahmens Teil ist.</span><span class="sxs-lookup"><span data-stu-id="8b8df-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b8df-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b8df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b8df-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="8b8df-106">[out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die Kette, enthält dieses Rahmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b8df-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b8df-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b8df-107">Requirements</span></span>  
 <span data-ttu-id="8b8df-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b8df-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b8df-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b8df-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b8df-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b8df-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b8df-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b8df-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
