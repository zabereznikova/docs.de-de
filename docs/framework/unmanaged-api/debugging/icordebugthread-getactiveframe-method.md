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
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133538"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="d49ed-102">ICorDebugThread::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="d49ed-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="d49ed-103">Ruft einen Schnittstellen Zeiger auf den aktiven (letzten) Frame dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="d49ed-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d49ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d49ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d49ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d49ed-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d49ed-106">vorgenommen Ein Zeiger auf die Adresse eines icorentbugframe-Schnittstellen Objekts, das einen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="d49ed-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d49ed-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d49ed-107">Remarks</span></span>  
 <span data-ttu-id="d49ed-108">Der `ppFrame`-Parameter ist NULL, wenn zurzeit kein Frame aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d49ed-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d49ed-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d49ed-109">Requirements</span></span>  
 <span data-ttu-id="d49ed-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d49ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d49ed-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d49ed-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d49ed-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d49ed-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d49ed-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d49ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
