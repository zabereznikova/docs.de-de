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
ms.openlocfilehash: 841af546cc3586529fe290c69e686438f634b90d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377782"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="9b784-102">ICorDebugThread2::GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="9b784-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="9b784-103">Ruft den Bezeichner der Aufgabe ab, die auf diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b784-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b784-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b784-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b784-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b784-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="9b784-106">vorgenommen Ein Zeiger auf den Bezeichner der Aufgabe, die auf dem Thread ausgeführt wird, der durch dieses ICorDebugThread2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9b784-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b784-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b784-107">Remarks</span></span>  
 <span data-ttu-id="9b784-108">Ein Task kann nur auf dem Thread ausgeführt werden, wenn der Thread einer Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9b784-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="9b784-109">`GetTaskID`gibt 0 (null) zurück, `pTaskId` Wenn der Thread keiner Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9b784-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b784-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b784-110">Requirements</span></span>  
 <span data-ttu-id="9b784-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b784-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b784-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b784-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b784-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b784-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b784-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b784-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
