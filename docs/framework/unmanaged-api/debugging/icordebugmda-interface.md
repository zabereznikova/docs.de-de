---
title: ICorDebugMDA-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA
helpviewer_keywords: ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00a003ee060de59fe0eb8ce8f740a620d77a7c85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="d9e65-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9e65-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="d9e65-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="d9e65-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9e65-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d9e65-104">Methods</span></span>  
  
|<span data-ttu-id="d9e65-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-105">Method</span></span>|<span data-ttu-id="d9e65-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9e65-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9e65-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="d9e65-108">Ruft eine Zeichenfolge, enthält eine Beschreibung dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="d9e65-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="d9e65-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="d9e65-110">Ruft die Flags, die dieser MDA zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9e65-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="d9e65-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="d9e65-112">Ruft eine Zeichenfolge mit dem Namen dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="d9e65-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="d9e65-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="d9e65-114">Ruft die Betriebssystem-Thread-ID auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9e65-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="d9e65-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e65-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="d9e65-116">Ruft den vollständigen XML-Stream dieser MDA zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9e65-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9e65-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9e65-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9e65-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d9e65-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e65-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9e65-119">Requirements</span></span>  
 <span data-ttu-id="d9e65-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e65-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e65-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9e65-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9e65-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9e65-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9e65-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e65-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e65-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9e65-124">See Also</span></span>  
 [<span data-ttu-id="d9e65-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9e65-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d9e65-126">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="d9e65-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
