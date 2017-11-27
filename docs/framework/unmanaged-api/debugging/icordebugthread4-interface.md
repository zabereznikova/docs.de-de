---
title: ICorDebugThread4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4
helpviewer_keywords: ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e54611a38193a05a33381e798a61977d7aec41a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="b8a0f-102">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8a0f-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="b8a0f-103">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8a0f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b8a0f-104">Methods</span></span>  
  
|<span data-ttu-id="b8a0f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b8a0f-105">Method</span></span>|<span data-ttu-id="b8a0f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8a0f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8a0f-107">GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="b8a0f-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="b8a0f-108">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) thread Blockierungsinformationen-Strukturen, die bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="b8a0f-109">HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="b8a0f-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="b8a0f-110">Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="b8a0f-111">GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="b8a0f-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="b8a0f-112">Ruft die aktuellen [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8a0f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8a0f-113">Remarks</span></span>  
 <span data-ttu-id="b8a0f-114">Diese Schnittstelle ist eine logische Erweiterung von der ICorDebugThread ICorDebugThread2, und [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8a0f-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b8a0f-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a0f-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8a0f-116">Requirements</span></span>  
 <span data-ttu-id="b8a0f-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a0f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a0f-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8a0f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8a0f-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8a0f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a0f-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a0f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a0f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a0f-121">See Also</span></span>  
 [<span data-ttu-id="b8a0f-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8a0f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b8a0f-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b8a0f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
