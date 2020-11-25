---
title: ICorDebugChain::GetActiveFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730135"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="10487-102">ICorDebugChain::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="10487-102">ICorDebugChain::GetActiveFrame Method</span></span>

<span data-ttu-id="10487-103">Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.</span><span class="sxs-lookup"><span data-stu-id="10487-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10487-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10487-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10487-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10487-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="10487-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Frame-Objekts, das den aktiven Frame (d. h. den aktuellen) Frame in der Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="10487-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10487-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10487-107">Remarks</span></span>  

 <span data-ttu-id="10487-108">Wenn kein verwalteter Stapel Rahmen verfügbar ist, `ppFrame` wird auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="10487-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="10487-109">Wenn der aktive Frame nicht verfügbar ist, wird der-Vorgang erfolgreich ausgeführt und ist `ppFrame` NULL.</span><span class="sxs-lookup"><span data-stu-id="10487-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="10487-110">Aktive Frames sind nicht für Ketten verfügbar, die aufgrund von CHAIN_ENTER_UNMANAGED initiiert wurden, und für einige Ketten, die aufgrund CHAIN_CLASS_INIT initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="10487-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="10487-111">Weitere Informationen finden Sie in der Cordebug-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="10487-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10487-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10487-112">Requirements</span></span>  

 <span data-ttu-id="10487-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10487-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10487-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10487-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10487-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10487-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10487-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10487-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
