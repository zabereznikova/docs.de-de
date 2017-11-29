---
title: ICorDebugController::EnumerateThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.EnumerateThreads
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7575bf2b50f11fab1c14f8fb28dc65e079c21de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="d53d0-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="d53d0-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="d53d0-103">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="d53d0-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d53d0-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d53d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d53d0-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="d53d0-106">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugThreadEnum", die einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d53d0-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d53d0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d53d0-107">Remarks</span></span>  
 <span data-ttu-id="d53d0-108">Ein Thread ist aktiviert, wenn betrachtet die [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) Rückruf hat weitergeleitet wurde und vor der [ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) Rückruf hat weitergeleitet wurde .</span><span class="sxs-lookup"><span data-stu-id="d53d0-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="d53d0-109">Ein verwalteter Thread kann keine verwalteten Frames nicht unbedingt auf einen Stapel auswirken.</span><span class="sxs-lookup"><span data-stu-id="d53d0-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="d53d0-110">Threads aufgelistet werden können, sogar noch bevor die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="d53d0-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="d53d0-111">Die Enumeration wird als natürlich leer sein.</span><span class="sxs-lookup"><span data-stu-id="d53d0-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d53d0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d53d0-112">Requirements</span></span>  
 <span data-ttu-id="d53d0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d53d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53d0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d53d0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d53d0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d53d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d53d0-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d53d0-117">See Also</span></span>  
 
