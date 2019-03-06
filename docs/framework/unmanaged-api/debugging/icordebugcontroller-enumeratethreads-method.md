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
ms.openlocfilehash: 6a4bb4072c574edeac1c531978fac75595c252e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481598"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="40e25-102">ICorDebugController::EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="40e25-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="40e25-103">Ruft einen Enumerator für die aktiv verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="40e25-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e25-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40e25-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40e25-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="40e25-106">[out] Ein Zeiger auf die Adresse des "ICorDebugThreadEnum"-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="40e25-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e25-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40e25-107">Remarks</span></span>  
 <span data-ttu-id="40e25-108">Ein Thread wird als aktiv betrachtet, nachdem die [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) Rückruf wurde gesendet wurden und vor der [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) Rückruf wurde gesendet wurden .</span><span class="sxs-lookup"><span data-stu-id="40e25-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="40e25-109">Ein verwalteter Thread kann nicht verwalteter Frames auf seinen Stapel unbedingt.</span><span class="sxs-lookup"><span data-stu-id="40e25-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="40e25-110">Threads aufgelistet werden können, sogar vor dem [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="40e25-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="40e25-111">Die Enumeration wird auf natürliche Weise leer sein.</span><span class="sxs-lookup"><span data-stu-id="40e25-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e25-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e25-112">Requirements</span></span>  
 <span data-ttu-id="40e25-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40e25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e25-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40e25-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40e25-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40e25-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40e25-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e25-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e25-117">See also</span></span>

