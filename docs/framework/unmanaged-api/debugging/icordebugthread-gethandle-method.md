---
title: ICorDebugThread::GetHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54981be7104eb04ac6347ad13b61a69f40d4377c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770620"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="dfb42-102">ICorDebugThread::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="dfb42-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="dfb42-103">Ruft das aktuelle Handle für den aktiven Teil des ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="dfb42-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfb42-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfb42-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="dfb42-106">[out] Ein Zeiger auf einen HTHREAD, der das Handle des aktiven Teils des Threads ist.</span><span class="sxs-lookup"><span data-stu-id="dfb42-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb42-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfb42-107">Remarks</span></span>  
 <span data-ttu-id="dfb42-108">Das Handle kann sich ändern, während der Prozess ausgeführt wird, und für die verschiedenen Teile des Threads kann abweichen.</span><span class="sxs-lookup"><span data-stu-id="dfb42-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="dfb42-109">Dieses Handle ist im Besitz der Debuggen-API.</span><span class="sxs-lookup"><span data-stu-id="dfb42-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="dfb42-110">Der Debugger sollte es vor der Verwendung duplizieren.</span><span class="sxs-lookup"><span data-stu-id="dfb42-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb42-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfb42-111">Requirements</span></span>  
 <span data-ttu-id="dfb42-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb42-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb42-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfb42-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfb42-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb42-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb42-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb42-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
