---
title: ICorDebug::SetUnmanagedHandler-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c1b6da9db047321583de8c3c9238ed9ad4d4ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="c39b6-102">ICorDebug::SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="c39b6-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="c39b6-103">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="c39b6-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c39b6-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c39b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c39b6-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="c39b6-106">[in] Ein Zeiger auf ein [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) -Objekt, das den Ereignishandler für nicht verwaltete Ereignisse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c39b6-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c39b6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c39b6-107">Remarks</span></span>  
 <span data-ttu-id="c39b6-108">Das Ereignishandlerobjekt für nicht verwaltete Ereignisse müssen festgelegt werden, nach einem Aufruf von [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) und vor allen Aufrufen [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) oder [ICorDebug:: DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39b6-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="c39b6-109">Allerdings werden für Legacyzwecke müssen nicht legen Sie das Ereignishandlerobjekt für nicht verwaltete Ereignisse, bis die erste systemeigene Debug-Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c39b6-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="c39b6-110">Insbesondere wenn `ICorDebug::CreateProcess` wurde das Flag CREATE_SUSPENDED, systemeigene Debug-Ereignisse nicht verteilt werden, bis der Haupt-Thread fortgesetzt wird festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c39b6-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c39b6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c39b6-111">Requirements</span></span>  
 <span data-ttu-id="c39b6-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c39b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c39b6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c39b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c39b6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c39b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c39b6-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c39b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39b6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c39b6-116">See Also</span></span>  
 [<span data-ttu-id="c39b6-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c39b6-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
