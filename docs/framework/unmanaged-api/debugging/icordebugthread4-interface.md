---
title: ICorDebugThread4-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f213a35a12bfb5cc92558a76e122a1494d567f93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170793"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="0171b-102">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0171b-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="0171b-103">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="0171b-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0171b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0171b-104">Methods</span></span>  
  
|<span data-ttu-id="0171b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0171b-105">Method</span></span>|<span data-ttu-id="0171b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0171b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0171b-107">GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="0171b-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="0171b-108">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) thread Blockierungsinformationen-Strukturen, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0171b-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="0171b-109">HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="0171b-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="0171b-110">Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0171b-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="0171b-111">GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="0171b-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="0171b-112">Ruft die aktuelle [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Objekt für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="0171b-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0171b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0171b-113">Remarks</span></span>  
 <span data-ttu-id="0171b-114">Diese Schnittstelle ist eine logische Erweiterung von der ICorDebugThread, ICorDebugThread2, und [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="0171b-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0171b-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0171b-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0171b-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0171b-116">Requirements</span></span>  
 <span data-ttu-id="0171b-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0171b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0171b-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0171b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0171b-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0171b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0171b-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0171b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0171b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0171b-121">See also</span></span>

- [<span data-ttu-id="0171b-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0171b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0171b-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0171b-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
