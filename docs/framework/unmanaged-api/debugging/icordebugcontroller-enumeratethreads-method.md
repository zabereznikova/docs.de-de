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
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892754"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="282d9-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="282d9-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="282d9-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="282d9-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="282d9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="282d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="282d9-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="282d9-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="282d9-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="282d9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="282d9-107">Remarks</span></span>  
 <span data-ttu-id="282d9-108">Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="282d9-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="282d9-109">Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="282d9-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="282d9-110">Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](icordebugmanagedcallback-createprocess-method.md) aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="282d9-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="282d9-111">Die Enumeration ist natürlich leer.</span><span class="sxs-lookup"><span data-stu-id="282d9-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="282d9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="282d9-112">Requirements</span></span>  
 <span data-ttu-id="282d9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="282d9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282d9-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="282d9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="282d9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="282d9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="282d9-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282d9-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="282d9-117">See also</span></span>
