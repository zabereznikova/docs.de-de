---
title: ICorDebugChain::GetReason-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: 58e40995012d98c1af6a41eb12d898c6b9b1d47b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719670"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="23937-102">ICorDebugChain::GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="23937-102">ICorDebugChain::GetReason Method</span></span>

<span data-ttu-id="23937-103">Ruft den Grund für die Entstehung dieser aufrufenden Kette ab.</span><span class="sxs-lookup"><span data-stu-id="23937-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23937-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23937-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23937-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23937-105">Parameters</span></span>  

 `pReason`  
 <span data-ttu-id="23937-106">vorgenommen Ein Zeiger auf einen Wert (eine bitweise Kombination) der CorDebugChainReason-Enumeration, die den Grund für die Entstehung dieser aufrufenden Kette angibt.</span><span class="sxs-lookup"><span data-stu-id="23937-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23937-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23937-107">Requirements</span></span>  

 <span data-ttu-id="23937-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23937-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23937-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23937-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23937-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23937-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23937-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23937-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
