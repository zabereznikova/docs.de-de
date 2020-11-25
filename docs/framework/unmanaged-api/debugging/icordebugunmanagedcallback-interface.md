---
title: ICorDebugUnmanagedCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: 73722c9fbc1571496159c32b0106f25bc05dbe65
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703017"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="c65ff-102">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c65ff-102">ICorDebugUnmanagedCallback Interface</span></span>

<span data-ttu-id="c65ff-103">Stellt Benachrichtigungen zu systemeigenen Ereignissen bereit, die nicht direkt mit dem Common Language Runtime (CLR) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c65ff-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c65ff-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c65ff-104">Methods</span></span>  
  
|<span data-ttu-id="c65ff-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c65ff-105">Method</span></span>|<span data-ttu-id="c65ff-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c65ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c65ff-107">DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="c65ff-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="c65ff-108">Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c65ff-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c65ff-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c65ff-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c65ff-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c65ff-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65ff-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c65ff-111">Requirements</span></span>  

 <span data-ttu-id="c65ff-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c65ff-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c65ff-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c65ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c65ff-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c65ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c65ff-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65ff-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c65ff-116">See also</span></span>

- [<span data-ttu-id="c65ff-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c65ff-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
