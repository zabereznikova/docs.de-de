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
ms.openlocfilehash: 41bd4c0bb4e84b6d6f267e24808baafa57f71882
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771116"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="9f5a9-102">ICorDebugThread::CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="9f5a9-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="9f5a9-103">Erstellt ein ICorDebugEval-Objekt, das erfasst und macht die Funktionalität dieses ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9f5a9-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f5a9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f5a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f5a9-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="9f5a9-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugEval` -Objekt, das erfasst und macht die Funktionalität dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="9f5a9-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f5a9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f5a9-107">Remarks</span></span>  
 <span data-ttu-id="9f5a9-108">Das Auswertungsobjekt wird eine neue Kette für den Thread vor seiner Berechnung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9f5a9-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="9f5a9-109">Dies unterbricht die Berechnung, die aktuell ausgeführte für den Thread bis zum Abschluss der Auswertung.</span><span class="sxs-lookup"><span data-stu-id="9f5a9-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f5a9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f5a9-110">Requirements</span></span>  
 <span data-ttu-id="9f5a9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f5a9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f5a9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f5a9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f5a9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f5a9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f5a9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5a9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
