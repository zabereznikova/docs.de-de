---
title: ICorDebugThread::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d01936481ec139757566d5b96cb95ea887cb8c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378057"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="c4851-102">ICorDebugThread::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="c4851-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="c4851-103">Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="c4851-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4851-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4851-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4851-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4851-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="c4851-106">vorgenommen Der Bezeichner des Threads.</span><span class="sxs-lookup"><span data-stu-id="c4851-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4851-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4851-107">Remarks</span></span>  
 <span data-ttu-id="c4851-108">Der Bezeichner des Betriebssystems kann sich möglicherweise während der Ausführung eines Prozesses ändern und kann einen anderen Wert für verschiedene Teile des Threads aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c4851-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4851-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4851-109">Requirements</span></span>  
 <span data-ttu-id="c4851-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4851-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4851-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4851-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4851-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4851-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4851-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4851-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
