---
title: ICorDebugThread::GetActiveChain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: e6b1d78b2bd95ea27f4b19a045cd2680342e8a80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728094"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="ffa9c-102">ICorDebugThread::GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="ffa9c-102">ICorDebugThread::GetActiveChain Method</span></span>

<span data-ttu-id="ffa9c-103">Ruft einen Schnittstellen Zeiger auf die aktive (letzte) Stapel Kette für dieses ICorDebugThread-Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="ffa9c-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffa9c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffa9c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ffa9c-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="ffa9c-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Stapel Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="ffa9c-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffa9c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ffa9c-107">Remarks</span></span>  

 <span data-ttu-id="ffa9c-108">Der- `ppChain` Parameter ist NULL, wenn derzeit keine Stapel Kette aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="ffa9c-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffa9c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ffa9c-109">Requirements</span></span>  

 <span data-ttu-id="ffa9c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa9c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa9c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffa9c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffa9c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffa9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffa9c-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
