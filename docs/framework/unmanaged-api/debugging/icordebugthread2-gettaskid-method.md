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
ms.openlocfilehash: 9b17a179745af65bde05527bd0157f3ce06c12c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678661"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="6ade8-102">ICorDebugThread2::GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="6ade8-102">ICorDebugThread2::GetTaskID Method</span></span>

<span data-ttu-id="6ade8-103">Ruft den Bezeichner der Aufgabe ab, die auf diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ade8-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ade8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ade8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ade8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ade8-105">Parameters</span></span>  

 `pTaskId`  
 <span data-ttu-id="6ade8-106">vorgenommen Ein Zeiger auf den Bezeichner der Aufgabe, die auf dem Thread ausgeführt wird, der durch dieses ICorDebugThread2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6ade8-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ade8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ade8-107">Remarks</span></span>  

 <span data-ttu-id="6ade8-108">Ein Task kann nur auf dem Thread ausgeführt werden, wenn der Thread einer Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6ade8-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="6ade8-109">`GetTaskID` gibt 0 (null) zurück, `pTaskId` Wenn der Thread keiner Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6ade8-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ade8-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6ade8-110">Requirements</span></span>  

 <span data-ttu-id="6ade8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ade8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ade8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ade8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ade8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ade8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ade8-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ade8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
