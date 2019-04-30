---
title: ICorDebugThread::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8eef616d51febd1b919e0a1936406551f441b98c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987102"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="42e91-102">ICorDebugThread::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="42e91-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="42e91-103">Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils des ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="42e91-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42e91-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e91-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42e91-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="42e91-106">[out] Der Bezeichner des Threads.</span><span class="sxs-lookup"><span data-stu-id="42e91-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e91-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42e91-107">Remarks</span></span>  
 <span data-ttu-id="42e91-108">Der Bezeichner des Betriebssystems während der Ausführung eines Prozesses ändern kann, und kann einen anderen Wert für die verschiedenen Teile des Threads sein.</span><span class="sxs-lookup"><span data-stu-id="42e91-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e91-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42e91-109">Requirements</span></span>  
 <span data-ttu-id="42e91-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e91-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42e91-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42e91-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42e91-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42e91-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
