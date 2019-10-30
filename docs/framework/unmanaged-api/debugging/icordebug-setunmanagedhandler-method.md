---
title: ICorDebug::SetUnmanagedHandler-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134047"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="77b8b-102">ICorDebug::SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="77b8b-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="77b8b-103">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="77b8b-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77b8b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77b8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77b8b-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="77b8b-106">in Ein Zeiger auf ein [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) -Objekt, das den Ereignishandler für nicht verwaltete Ereignisse darstellt.</span><span class="sxs-lookup"><span data-stu-id="77b8b-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77b8b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77b8b-107">Remarks</span></span>  
 <span data-ttu-id="77b8b-108">Das Ereignishandlerobjekt für nicht verwaltete Ereignisse muss nach einem Aufruf von [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) und vor allen Aufrufen von [ICorDebug:: deateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) oder [ICorDebug::D ebugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="77b8b-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="77b8b-109">Allerdings müssen Sie für Legacy Zwecke das Ereignishandlerobjekt nicht für nicht verwaltete Ereignisse festlegen, bis das erste systemeigene Debugereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="77b8b-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="77b8b-110">Insbesondere, wenn `ICorDebug::CreateProcess` das CREATE_SUSPENDED-Flag festgelegt hat, können systemeigene Debugereignisse erst weitergeleitet werden, wenn der Haupt Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="77b8b-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77b8b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77b8b-111">Requirements</span></span>  
 <span data-ttu-id="77b8b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77b8b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77b8b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77b8b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77b8b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77b8b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77b8b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77b8b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b8b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77b8b-116">See also</span></span>

- [<span data-ttu-id="77b8b-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77b8b-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
