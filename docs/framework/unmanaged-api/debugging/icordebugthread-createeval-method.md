---
title: ICorDebugThread::CreateEval-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 766677d9eef60c811c8537bc60bb8db29dd988c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="f8a1c-102">ICorDebugThread::CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="f8a1c-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="f8a1c-103">Erstellt ein ICorDebugEval-Objekt, das erfasst und die Funktionen dieses ICorDebugThread verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f8a1c-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8a1c-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8a1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8a1c-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="f8a1c-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugEval` Objekt, das erfasst und die Funktionen dieses Threads verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f8a1c-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a1c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8a1c-107">Remarks</span></span>  
 <span data-ttu-id="f8a1c-108">Das Auswertungsobjekt wird eine neue Kette für den Thread push, vor dem Ausführen von seiner Berechnung.</span><span class="sxs-lookup"><span data-stu-id="f8a1c-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="f8a1c-109">Dies unterbricht die Berechnung, die derzeit ausgeführten für den Thread bis zum Abschluss der Auswertung.</span><span class="sxs-lookup"><span data-stu-id="f8a1c-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a1c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8a1c-110">Requirements</span></span>  
 <span data-ttu-id="f8a1c-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a1c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a1c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8a1c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8a1c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8a1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8a1c-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
