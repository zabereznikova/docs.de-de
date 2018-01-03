---
title: ICorDebugChain::GetReason-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c23385c0d7b6173659e071735dee5d2d75a9e33a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="094e2-102">ICorDebugChain::GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="094e2-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="094e2-103">Ruft den Grund für die Entstehung dieser Aufrufkette ab.</span><span class="sxs-lookup"><span data-stu-id="094e2-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="094e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="094e2-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="094e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="094e2-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="094e2-106">[out] Ein Zeiger auf einen Wert (eine bitweise Kombination) der CorDebugChainReason-Enumeration, die den Grund für die Entstehung dieser Aufrufkette angibt.</span><span class="sxs-lookup"><span data-stu-id="094e2-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="094e2-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="094e2-107">Requirements</span></span>  
 <span data-ttu-id="094e2-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="094e2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="094e2-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="094e2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="094e2-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="094e2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="094e2-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="094e2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
