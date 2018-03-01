---
title: ICorDebugThread4-Schnittstelle
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
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0066fbda63e46442cc6b6b6547ad7f0393815840
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="10331-102">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10331-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="10331-103">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="10331-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10331-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10331-104">Methods</span></span>  
  
|<span data-ttu-id="10331-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10331-105">Method</span></span>|<span data-ttu-id="10331-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10331-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10331-107">GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="10331-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="10331-108">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) thread Blockierungsinformationen-Strukturen, die bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10331-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="10331-109">HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="10331-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="10331-110">Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="10331-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="10331-111">GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="10331-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="10331-112">Ruft die aktuellen [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="10331-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10331-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10331-113">Remarks</span></span>  
 <span data-ttu-id="10331-114">Diese Schnittstelle ist eine logische Erweiterung von der ICorDebugThread ICorDebugThread2, und [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="10331-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10331-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="10331-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10331-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10331-116">Requirements</span></span>  
 <span data-ttu-id="10331-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10331-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10331-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10331-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10331-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10331-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10331-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10331-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10331-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10331-121">See Also</span></span>  
 [<span data-ttu-id="10331-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10331-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="10331-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="10331-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
