---
title: ICorDebugChain::GetActiveFrame-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b5de327c1579d05f6ae4a440fc76a3fb9ee99b13
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="4b25d-102">ICorDebugChain::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="4b25d-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="4b25d-103">Ruft den aktiven (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="4b25d-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b25d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b25d-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b25d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b25d-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="4b25d-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFrame-Objekts, das den aktiven darstellt (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="4b25d-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b25d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b25d-107">Remarks</span></span>  
 <span data-ttu-id="4b25d-108">Wenn kein verwalteter Stapelrahmen verfügbar ist, wird `ppFrame` ist festgelegt auf Null.</span><span class="sxs-lookup"><span data-stu-id="4b25d-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="4b25d-109">Wenn der aktive Frame nicht verfügbar ist, wird der Aufruf erfolgreich und `ppFrame` wird null sein.</span><span class="sxs-lookup"><span data-stu-id="4b25d-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="4b25d-110">Aktive Frames werden nicht für Ketten durch CHAIN_ENTER_UNMANAGED initiiert wurden, und einige Ketten durch CHAIN_CLASS_INIT initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4b25d-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="4b25d-111">Finden Sie unter CorDebugChainReason-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4b25d-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b25d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b25d-112">Requirements</span></span>  
 <span data-ttu-id="4b25d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b25d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b25d-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b25d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b25d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b25d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b25d-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b25d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
