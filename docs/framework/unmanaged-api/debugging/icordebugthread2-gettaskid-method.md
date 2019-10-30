---
title: ICorDebugThread2::GetTaskID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: d5f2838007504e56ad44614a6778083be046629f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140073"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="9d9ff-102">ICorDebugThread2::GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="9d9ff-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="9d9ff-103">Ruft den Bezeichner der Aufgabe ab, die auf diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d9ff-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d9ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d9ff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d9ff-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="9d9ff-106">vorgenommen Ein Zeiger auf den Bezeichner der Aufgabe, die auf dem Thread ausgeführt wird, der durch dieses ICorDebugThread2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9d9ff-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d9ff-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d9ff-107">Remarks</span></span>  
 <span data-ttu-id="9d9ff-108">Ein Task kann nur auf dem Thread ausgeführt werden, wenn der Thread einer Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9d9ff-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="9d9ff-109">`GetTaskID` gibt in `pTaskId` 0 (null) zurück, wenn der Thread keiner Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9d9ff-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d9ff-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d9ff-110">Requirements</span></span>  
 <span data-ttu-id="9d9ff-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d9ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d9ff-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d9ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d9ff-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d9ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d9ff-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d9ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
