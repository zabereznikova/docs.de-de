---
title: ICorDebugProcess2::GetThreadForTaskID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa1f6852544dddcdf514b14710ade3949818c93e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487312"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="5daf8-102">ICorDebugProcess2::GetThreadForTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="5daf8-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="5daf8-103">Ruft den Thread, der auf dem die Aufgabe mit der angegebenen ID ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5daf8-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5daf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5daf8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5daf8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5daf8-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="5daf8-106">[in] Der Bezeichner der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="5daf8-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="5daf8-107">[out] Ein Zeiger auf die Adresse des ICorDebugThread2-Objekts, die der Thread darstellt, abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5daf8-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5daf8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5daf8-108">Remarks</span></span>  
 <span data-ttu-id="5daf8-109">Der Host kann die Task-ID festlegen, mit der [ICLRTask:: SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5daf8-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5daf8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5daf8-110">Requirements</span></span>  
 <span data-ttu-id="5daf8-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5daf8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5daf8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5daf8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5daf8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5daf8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5daf8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5daf8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
