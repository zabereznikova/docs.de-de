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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f8276e2a8fd1bdc546add2ae1ca5d96298186c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412830"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="c5dba-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="c5dba-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="c5dba-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="c5dba-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5dba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5dba-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5dba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5dba-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="c5dba-106">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugThreadEnum", die einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="c5dba-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5dba-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5dba-107">Remarks</span></span>  
 <span data-ttu-id="c5dba-108">Ein Thread ist aktiviert, wenn betrachtet die [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) Rückruf hat weitergeleitet wurde und vor der [ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) Rückruf hat weitergeleitet wurde .</span><span class="sxs-lookup"><span data-stu-id="c5dba-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="c5dba-109">Ein verwalteter Thread kann keine verwalteten Frames nicht unbedingt auf einen Stapel auswirken.</span><span class="sxs-lookup"><span data-stu-id="c5dba-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="c5dba-110">Threads aufgelistet werden können, sogar noch bevor die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="c5dba-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="c5dba-111">Die Enumeration wird als natürlich leer sein.</span><span class="sxs-lookup"><span data-stu-id="c5dba-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5dba-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5dba-112">Requirements</span></span>  
 <span data-ttu-id="c5dba-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5dba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5dba-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5dba-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5dba-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5dba-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5dba-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5dba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5dba-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5dba-117">See Also</span></span>  
 
