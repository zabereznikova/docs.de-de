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
ms.openlocfilehash: 70e79378ad8eb2599199a1f7bc57cf530c9b4dd3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379691"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="91466-102">ICorDebugThread::GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="91466-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="91466-103">Ruft einen Schnittstellen Zeiger auf die aktive (letzte) Stapel Kette für dieses ICorDebugThread-Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="91466-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91466-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91466-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91466-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91466-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="91466-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Stapel Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="91466-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91466-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91466-107">Remarks</span></span>  
 <span data-ttu-id="91466-108">Der- `ppChain` Parameter ist NULL, wenn derzeit keine Stapel Kette aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="91466-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91466-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="91466-109">Requirements</span></span>  
 <span data-ttu-id="91466-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91466-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91466-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91466-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91466-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91466-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91466-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91466-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
