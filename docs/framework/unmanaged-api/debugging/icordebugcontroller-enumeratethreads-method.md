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
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125407"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="fd3e0-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3e0-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="fd3e0-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd3e0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd3e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd3e0-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="fd3e0-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd3e0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd3e0-107">Remarks</span></span>  
 <span data-ttu-id="fd3e0-108">Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="fd3e0-109">Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="fd3e0-110">Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="fd3e0-111">Die Enumeration ist natürlich leer.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3e0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd3e0-112">Requirements</span></span>  
 <span data-ttu-id="fd3e0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3e0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd3e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd3e0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd3e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd3e0-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3e0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd3e0-117">See also</span></span>
