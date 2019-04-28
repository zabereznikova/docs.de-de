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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645369"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="4133b-102">ICorDebugChain::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="4133b-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="4133b-103">Ruft das aktive (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="4133b-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4133b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4133b-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4133b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4133b-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="4133b-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFrame-Objekts, das den aktiven darstellt (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="4133b-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4133b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4133b-107">Remarks</span></span>  
 <span data-ttu-id="4133b-108">Wenn kein verwalteter Stapelrahmen verfügbar ist, `ppFrame` wird festgelegt auf Null.</span><span class="sxs-lookup"><span data-stu-id="4133b-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="4133b-109">Wenn der aktive Frame nicht verfügbar ist, wird der Aufruf erfolgreich und `ppFrame` NULL.</span><span class="sxs-lookup"><span data-stu-id="4133b-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="4133b-110">Aktiven Frames sind nicht verfügbar für Ketten durch CHAIN_ENTER_UNMANAGED initiiert wurden, und für einige Ketten durch CHAIN_CLASS_INIT initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4133b-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="4133b-111">Finden Sie unter der CorDebugChainReason-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4133b-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4133b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4133b-112">Requirements</span></span>  
 <span data-ttu-id="4133b-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4133b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4133b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4133b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4133b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4133b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4133b-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4133b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
