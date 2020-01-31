---
title: ICorDebugController::EnumerateThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783792"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="9c4c8-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="9c4c8-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="9c4c8-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c4c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c4c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c4c8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9c4c8-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="9c4c8-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c4c8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c4c8-107">Remarks</span></span>  
 <span data-ttu-id="9c4c8-108">Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="9c4c8-109">Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="9c4c8-110">Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](icordebugmanagedcallback-createprocess-method.md) aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="9c4c8-111">Die Enumeration ist natürlich leer.</span><span class="sxs-lookup"><span data-stu-id="9c4c8-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c4c8-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c4c8-112">Requirements</span></span>  
 <span data-ttu-id="9c4c8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c4c8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c4c8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c4c8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c4c8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c4c8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c4c8-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c4c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4c8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c4c8-117">See also</span></span>
