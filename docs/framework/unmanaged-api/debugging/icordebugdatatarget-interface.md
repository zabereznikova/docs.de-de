---
title: ICorDebugDataTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53c054b59376a78eda83181e75aec94548e92f17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499817"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="cd9a6-102">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd9a6-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="cd9a6-103">Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd9a6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cd9a6-104">Methods</span></span>  
  
|<span data-ttu-id="cd9a6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cd9a6-105">Method</span></span>|<span data-ttu-id="cd9a6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd9a6-107">GetPlatform-Methode</span><span class="sxs-lookup"><span data-stu-id="cd9a6-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="cd9a6-108">Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf dem der Zielprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="cd9a6-109">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="cd9a6-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="cd9a6-110">Ruft einen Block zusammenhängender Arbeitsspeicher, die beginnend ab der angegebenen Adresse, und der angegebene Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="cd9a6-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="cd9a6-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="cd9a6-112">Fordert den Kontext des aktuellen Threads für den angegebenen Thread an.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd9a6-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd9a6-113">Remarks</span></span>  
 <span data-ttu-id="cd9a6-114">`ICorDebugDataTarget` und seine Methoden weisen folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="cd9a6-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
-   <span data-ttu-id="cd9a6-115">Die Debuggen von Diensten rufen Methoden für diese Schnittstelle zum Zugriff auf Speicher und andere Daten in den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
-   <span data-ttu-id="cd9a6-116">Der Debuggerclient muss diese Schnittstelle nach Bedarf für die betreffende Zielframework (z. B. einen aktiven Prozess oder ein Speicherabbild) implementieren.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
-   <span data-ttu-id="cd9a6-117">Die `ICorDebugDataTarget` Methoden können nur aus aufgerufen werden, innerhalb von Methoden, die in anderen implementiert `ICorDebug*` Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="cd9a6-118">Dadurch wird sichergestellt, dass der Debuggerclient steuern kann, über welchem Thread sie auf und wann aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
-   <span data-ttu-id="cd9a6-119">Die `ICorDebugDataTarget` Implementierung muss immer auf dem neuesten Stand Informationen über das Ziel zurück.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="cd9a6-120">Der Zielprozess beendet und in keiner Weise bei der nicht geändert werden sollten `ICorDebug*` Schnittstellen (und somit auch `ICorDebugDataTarget` Methoden) aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="cd9a6-121">Wenn das Ziel ein, und dessen Zustand ändert, ist die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode muss erneut aufgerufen, um ein Ersatz-ICorDebugProcess-Instanz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd9a6-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cd9a6-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9a6-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9a6-123">Requirements</span></span>  
 <span data-ttu-id="cd9a6-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd9a6-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9a6-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd9a6-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd9a6-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd9a6-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd9a6-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9a6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9a6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd9a6-128">See also</span></span>
- [<span data-ttu-id="cd9a6-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd9a6-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd9a6-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cd9a6-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
