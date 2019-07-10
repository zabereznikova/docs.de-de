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
ms.openlocfilehash: 1272df17a9a9a500b84f62914811b8d109bf3cdd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768954"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="03b7e-102">ICorDebugThread2::GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="03b7e-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="03b7e-103">Ruft den Bezeichner des Tasks in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03b7e-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03b7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03b7e-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="03b7e-106">[out] Ein Zeiger auf den Bezeichner der Aufgabe ausgeführt, die für den Thread, der von diesem ICorDebugThread2-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="03b7e-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b7e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03b7e-107">Remarks</span></span>  
 <span data-ttu-id="03b7e-108">Eine Aufgabe kann nur auf dem Thread ausgeführt werden, wenn der Thread mit einer Verbindung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="03b7e-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="03b7e-109">`GetTaskID` Gibt NULL zurück, `pTaskId` , wenn der Thread nicht mit einer Verbindung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="03b7e-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b7e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03b7e-110">Requirements</span></span>  
 <span data-ttu-id="03b7e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03b7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b7e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03b7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03b7e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03b7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03b7e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
