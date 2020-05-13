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
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379281"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="6f789-102">ICorDebugThread::CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="6f789-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="6f789-103">Erstellt ein ICorDebugEval-Objekt, das die Funktionalität dieses ICorDebugThread sammelt und verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="6f789-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f789-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f789-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f789-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f789-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="6f789-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugEval` Objekts, das die Funktionalität dieses Threads sammelt und verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="6f789-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f789-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f789-107">Remarks</span></span>  
 <span data-ttu-id="6f789-108">Das Auswertungs Objekt überträgt eine neue Kette im Thread, bevor die Berechnung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6f789-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="6f789-109">Dadurch wird die derzeit auf dem Thread ausgeführte Berechnung unterbrochen, bis die Auswertung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6f789-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f789-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f789-110">Requirements</span></span>  
 <span data-ttu-id="6f789-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f789-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f789-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f789-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f789-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f789-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f789-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f789-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
