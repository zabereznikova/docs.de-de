---
title: ICorDebugMDA-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550b39445dfe4d97e712e9a4c73aa0f497b3fce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420965"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="ca460-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca460-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="ca460-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="ca460-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca460-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca460-104">Methods</span></span>  
  
|<span data-ttu-id="ca460-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-105">Method</span></span>|<span data-ttu-id="ca460-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca460-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca460-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="ca460-108">Ruft eine Zeichenfolge, enthält eine Beschreibung dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="ca460-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="ca460-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="ca460-110">Ruft die Flags, die dieser MDA zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ca460-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="ca460-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="ca460-112">Ruft eine Zeichenfolge mit dem Namen dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="ca460-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="ca460-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="ca460-114">Ruft die Betriebssystem-Thread-ID auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca460-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="ca460-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="ca460-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="ca460-116">Ruft den vollständigen XML-Stream dieser MDA zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ca460-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca460-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca460-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca460-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ca460-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca460-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca460-119">Requirements</span></span>  
 <span data-ttu-id="ca460-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca460-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca460-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca460-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca460-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca460-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca460-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca460-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca460-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca460-124">See Also</span></span>  
 [<span data-ttu-id="ca460-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca460-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ca460-126">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="ca460-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
