---
title: ICorDebugUnmanagedCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa104bee5171b3b28731cf18a4d26e32f49169ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="322c4-102">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="322c4-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="322c4-103">Ermöglicht die Benachrichtigung über systemeigene Ereignisse, die nicht direkt auf die common Language Runtime (CLR) beziehen.</span><span class="sxs-lookup"><span data-stu-id="322c4-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="322c4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="322c4-104">Methods</span></span>  
  
|<span data-ttu-id="322c4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="322c4-105">Method</span></span>|<span data-ttu-id="322c4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="322c4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="322c4-107">DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="322c4-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="322c4-108">Benachrichtigt den Debugger, dass ein systemeigenes Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="322c4-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="322c4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="322c4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="322c4-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="322c4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="322c4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="322c4-111">Requirements</span></span>  
 <span data-ttu-id="322c4-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="322c4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="322c4-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="322c4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="322c4-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="322c4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="322c4-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="322c4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322c4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="322c4-116">See Also</span></span>  
 [<span data-ttu-id="322c4-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="322c4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
