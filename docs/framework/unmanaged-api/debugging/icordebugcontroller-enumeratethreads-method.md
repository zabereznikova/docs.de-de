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
ms.openlocfilehash: f98118f9206d9ccd7dc9dc9a943500c7b4cd676a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732657"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="f1e70-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f1e70-102">ICorDebugController::EnumerateThreads Method</span></span>

<span data-ttu-id="f1e70-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f1e70-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1e70-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1e70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1e70-105">Parameters</span></span>  

 `ppThreads`  
 <span data-ttu-id="f1e70-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="f1e70-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1e70-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1e70-107">Remarks</span></span>  

 <span data-ttu-id="f1e70-108">Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f1e70-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="f1e70-109">Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="f1e70-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="f1e70-110">Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](icordebugmanagedcallback-createprocess-method.md) aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="f1e70-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="f1e70-111">Die Enumeration ist natürlich leer.</span><span class="sxs-lookup"><span data-stu-id="f1e70-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e70-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1e70-112">Requirements</span></span>  

 <span data-ttu-id="f1e70-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1e70-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e70-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1e70-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1e70-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1e70-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1e70-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1e70-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e70-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1e70-117">See also</span></span>
