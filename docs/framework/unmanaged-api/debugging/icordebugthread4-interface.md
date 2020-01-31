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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791336"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="8a3ff-102">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a3ff-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="8a3ff-103">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a3ff-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8a3ff-104">Methods</span></span>  
  
|<span data-ttu-id="8a3ff-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="8a3ff-105">Method</span></span>|<span data-ttu-id="8a3ff-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a3ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a3ff-107">GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="8a3ff-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="8a3ff-108">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="8a3ff-109">HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="8a3ff-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="8a3ff-110">Gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="8a3ff-111">GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="8a3ff-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="8a3ff-112">Ruft das aktuelle [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Objekt für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3ff-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a3ff-113">Remarks</span></span>  
 <span data-ttu-id="8a3ff-114">Diese Schnittstelle ist eine logische Erweiterung der Schnittstellen ICorDebugThread, ICorDebugThread2 und [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8a3ff-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a3ff-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8a3ff-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3ff-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a3ff-116">Requirements</span></span>  
 <span data-ttu-id="8a3ff-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3ff-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3ff-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a3ff-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a3ff-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a3ff-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a3ff-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3ff-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3ff-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a3ff-121">See also</span></span>

- [<span data-ttu-id="8a3ff-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8a3ff-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a3ff-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8a3ff-123">Debugging</span></span>](index.md)
