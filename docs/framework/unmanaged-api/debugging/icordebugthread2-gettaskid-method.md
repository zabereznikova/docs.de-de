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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5690856b526bf0f7bc4527d04ae8044cda1f6e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417865"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="ef619-102">ICorDebugThread2::GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="ef619-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="ef619-103">Ruft den Bezeichner des Tasks in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef619-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef619-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef619-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef619-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef619-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="ef619-106">[out] Ein Zeiger auf den Bezeichner der Aufgabe, die Ausführung für den Thread, der von diesem ICorDebugThread2-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef619-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef619-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef619-107">Remarks</span></span>  
 <span data-ttu-id="ef619-108">Eine Aufgabe kann nur auf dem Thread ausgeführt werden, wenn der Thread eine Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ef619-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="ef619-109">`GetTaskID` Gibt NULL zurück, `pTaskId` , wenn der Thread nicht mit einer Verbindung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ef619-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef619-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef619-110">Requirements</span></span>  
 <span data-ttu-id="ef619-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef619-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef619-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef619-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef619-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef619-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef619-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef619-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
