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
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769966"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="45ebf-102">ICorDebugThread::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="45ebf-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="45ebf-103">Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils des ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="45ebf-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ebf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45ebf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45ebf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45ebf-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="45ebf-106">[out] Der Bezeichner des Threads.</span><span class="sxs-lookup"><span data-stu-id="45ebf-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45ebf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45ebf-107">Remarks</span></span>  
 <span data-ttu-id="45ebf-108">Der Bezeichner des Betriebssystems während der Ausführung eines Prozesses ändern kann, und kann einen anderen Wert für die verschiedenen Teile des Threads sein.</span><span class="sxs-lookup"><span data-stu-id="45ebf-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45ebf-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45ebf-109">Requirements</span></span>  
 <span data-ttu-id="45ebf-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45ebf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ebf-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45ebf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45ebf-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45ebf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45ebf-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ebf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
