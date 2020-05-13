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
ms.openlocfilehash: a0d6f3e109f92ad44eeeb1b1dec05e53015992a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378361"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="bf78e-102">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf78e-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="bf78e-103">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="bf78e-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf78e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bf78e-104">Methods</span></span>  
  
|<span data-ttu-id="bf78e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bf78e-105">Method</span></span>|<span data-ttu-id="bf78e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf78e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf78e-107">GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="bf78e-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="bf78e-108">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bf78e-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="bf78e-109">HadUnhandledException-Methode</span><span class="sxs-lookup"><span data-stu-id="bf78e-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="bf78e-110">Gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bf78e-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="bf78e-111">GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="bf78e-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="bf78e-112">Ruft das aktuelle [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Objekt für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="bf78e-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf78e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf78e-113">Remarks</span></span>  
 <span data-ttu-id="bf78e-114">Diese Schnittstelle ist eine logische Erweiterung der Schnittstellen ICorDebugThread, ICorDebugThread2 und [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bf78e-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf78e-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bf78e-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf78e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bf78e-116">Requirements</span></span>  
 <span data-ttu-id="bf78e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf78e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf78e-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf78e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf78e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf78e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf78e-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf78e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf78e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf78e-121">See also</span></span>

- [<span data-ttu-id="bf78e-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bf78e-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="bf78e-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bf78e-123">Debugging</span></span>](index.md)
