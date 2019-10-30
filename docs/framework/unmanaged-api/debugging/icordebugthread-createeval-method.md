---
title: ICorDebugThread::CreateEval-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 0c622e0eba27f501446d2b7d9d264ee0834e869c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133620"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="c6d71-102">ICorDebugThread::CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d71-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="c6d71-103">Erstellt ein ICorDebugEval-Objekt, das die Funktionalität dieses ICorDebugThread sammelt und verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c6d71-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d71-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6d71-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6d71-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6d71-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="c6d71-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugEval` Objekts, das die Funktionalität dieses Threads sammelt und verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c6d71-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6d71-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6d71-107">Remarks</span></span>  
 <span data-ttu-id="c6d71-108">Das Auswertungs Objekt überträgt eine neue Kette im Thread, bevor die Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6d71-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="c6d71-109">Dadurch wird die derzeit auf dem Thread ausgeführte Berechnung unterbrochen, bis die Auswertung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c6d71-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d71-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6d71-110">Requirements</span></span>  
 <span data-ttu-id="c6d71-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d71-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d71-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d71-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d71-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d71-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d71-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d71-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
