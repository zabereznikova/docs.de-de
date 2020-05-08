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
ms.openlocfilehash: 54272dd18a12715bab58ec1b1a4c1dc00e4bf12b
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976524"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="34781-102">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34781-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="34781-103">Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.</span><span class="sxs-lookup"><span data-stu-id="34781-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34781-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="34781-104">Methods</span></span>  
  
|<span data-ttu-id="34781-105">Methode</span><span class="sxs-lookup"><span data-stu-id="34781-105">Method</span></span>|<span data-ttu-id="34781-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="34781-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34781-107">GetPlatform-Methode</span><span class="sxs-lookup"><span data-stu-id="34781-107">GetPlatform Method</span></span>](icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="34781-108">Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34781-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="34781-109">ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="34781-109">ReadVirtual Method</span></span>](icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="34781-110">Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="34781-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="34781-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="34781-111">GetThreadContext Method</span></span>](icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="34781-112">Fordert den aktuellen Thread Kontext für den angegebenen Thread an.</span><span class="sxs-lookup"><span data-stu-id="34781-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34781-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34781-113">Remarks</span></span>  
 <span data-ttu-id="34781-114">`ICorDebugDataTarget`und die zugehörigen Methoden haben die folgenden Merkmale:</span><span class="sxs-lookup"><span data-stu-id="34781-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="34781-115">Die Debugdienste aufrufen Methoden für diese Schnittstelle, um auf Arbeitsspeicher und andere Daten im Ziel Prozess zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="34781-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="34781-116">Der Debugger-Client muss diese Schnittstelle entsprechend für das jeweilige Ziel implementieren (z. b. einen Live Prozess oder ein Speicher Abbild).</span><span class="sxs-lookup"><span data-stu-id="34781-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="34781-117">Die `ICorDebugDataTarget` Methoden können nur innerhalb von Methoden aufgerufen werden, die in `ICorDebug*` anderen Schnittstellen implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="34781-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="34781-118">Dadurch wird sichergestellt, dass der Debugger-Client steuern kann, in welchem Thread er aufgerufen wird, und wann.</span><span class="sxs-lookup"><span data-stu-id="34781-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="34781-119">Die `ICorDebugDataTarget` -Implementierung muss immer aktuelle Informationen über das Ziel zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="34781-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="34781-120">Der Ziel Prozess sollte beendet und in keiner Weise geändert werden, während `ICorDebug*` Schnittstellen (und `ICorDebugDataTarget` somit Methoden) aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34781-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="34781-121">Wenn es sich bei dem Ziel um einen Live Prozess handelt und der Status geändert wird, muss die [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode erneut aufgerufen werden, um eine ICorDebugProcess-Ersetzungs Instanz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34781-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34781-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34781-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34781-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34781-123">Requirements</span></span>  
 <span data-ttu-id="34781-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34781-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34781-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34781-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34781-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34781-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34781-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34781-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34781-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34781-128">See also</span></span>

- [<span data-ttu-id="34781-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="34781-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="34781-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="34781-130">Debugging</span></span>](index.md)
