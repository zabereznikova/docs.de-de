---
title: ICorDebugThread::GetActiveFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 6ca4c1ad5ef575db075a5066146bacb6d1e59ea2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728081"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="aab42-102">ICorDebugThread::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="aab42-102">ICorDebugThread::GetActiveFrame Method</span></span>

<span data-ttu-id="aab42-103">Ruft einen Schnittstellen Zeiger auf den aktiven (letzten) Frame dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="aab42-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aab42-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aab42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aab42-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="aab42-106">vorgenommen Ein Zeiger auf die Adresse eines icorentbugframe-Schnittstellen Objekts, das einen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="aab42-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aab42-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aab42-107">Remarks</span></span>  

 <span data-ttu-id="aab42-108">Der- `ppFrame` Parameter ist NULL, wenn zurzeit kein Frame aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="aab42-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab42-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aab42-109">Requirements</span></span>  

 <span data-ttu-id="aab42-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aab42-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab42-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aab42-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aab42-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aab42-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aab42-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aab42-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
