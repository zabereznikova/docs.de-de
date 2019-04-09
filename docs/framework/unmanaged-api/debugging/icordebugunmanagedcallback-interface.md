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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a1546068ae6a8c8be1c0af1ef3c7d770c23d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128675"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="ac73f-102">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac73f-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="ac73f-103">Ermöglicht die Benachrichtigung über systemeigene Ereignisse, die nicht direkt auf die common Language Runtime (CLR) beziehen.</span><span class="sxs-lookup"><span data-stu-id="ac73f-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac73f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ac73f-104">Methods</span></span>  
  
|<span data-ttu-id="ac73f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ac73f-105">Method</span></span>|<span data-ttu-id="ac73f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac73f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac73f-107">DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="ac73f-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="ac73f-108">Benachrichtigt den Debugger, dass ein systemeigenes Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ac73f-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac73f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac73f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac73f-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ac73f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac73f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac73f-111">Requirements</span></span>  
 <span data-ttu-id="ac73f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac73f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac73f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac73f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac73f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac73f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ac73f-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ac73f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ac73f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac73f-116">See also</span></span>

- [<span data-ttu-id="ac73f-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ac73f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
