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
ms.openlocfilehash: 0bce14a6853c872d27057b9fffc32b54c59abf13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723388"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="0504c-102">ICorDebug::SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="0504c-102">ICorDebug::SetUnmanagedHandler Method</span></span>

<span data-ttu-id="0504c-103">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="0504c-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0504c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0504c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0504c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0504c-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="0504c-106">in Ein Zeiger auf ein [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) -Objekt, das den Ereignishandler für nicht verwaltete Ereignisse darstellt.</span><span class="sxs-lookup"><span data-stu-id="0504c-106">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0504c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0504c-107">Remarks</span></span>  

 <span data-ttu-id="0504c-108">Das Ereignishandlerobjekt für nicht verwaltete Ereignisse muss nach einem Aufruf von [ICorDebug:: Initialize](icordebug-initialize-method.md) und vor allen Aufrufen von [ICorDebug:: deateprocess](icordebug-createprocess-method.md) oder [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md)festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0504c-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="0504c-109">Allerdings müssen Sie für Legacy Zwecke das Ereignishandlerobjekt nicht für nicht verwaltete Ereignisse festlegen, bis das erste systemeigene Debugereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0504c-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="0504c-110">Insbesondere, wenn `ICorDebug::CreateProcess` das CREATE_SUSPENDED-Flag festgelegt hat, können systemeigene Debugereignisse erst weitergeleitet werden, wenn der Haupt Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0504c-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0504c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0504c-111">Requirements</span></span>  

 <span data-ttu-id="0504c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0504c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0504c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0504c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0504c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0504c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0504c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0504c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0504c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0504c-116">See also</span></span>

- [<span data-ttu-id="0504c-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0504c-117">ICorDebug Interface</span></span>](icordebug-interface.md)
