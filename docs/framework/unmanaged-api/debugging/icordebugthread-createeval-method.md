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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480662"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="9ea05-102">ICorDebugThread::CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="9ea05-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="9ea05-103">Erstellt ein ICorDebugEval-Objekt, das erfasst und macht die Funktionalität dieses ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9ea05-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ea05-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ea05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ea05-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="9ea05-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugEval` -Objekt, das erfasst und macht die Funktionalität dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="9ea05-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ea05-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ea05-107">Remarks</span></span>  
 <span data-ttu-id="9ea05-108">Das Auswertungsobjekt wird eine neue Kette für den Thread vor seiner Berechnung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9ea05-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="9ea05-109">Dies unterbricht die Berechnung, die aktuell ausgeführte für den Thread bis zum Abschluss der Auswertung.</span><span class="sxs-lookup"><span data-stu-id="9ea05-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea05-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ea05-110">Requirements</span></span>  
 <span data-ttu-id="9ea05-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea05-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ea05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ea05-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ea05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ea05-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
