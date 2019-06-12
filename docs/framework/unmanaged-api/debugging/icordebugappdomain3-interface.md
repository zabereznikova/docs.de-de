---
title: ICorDebugAppDomain3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025892"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="b0bee-102">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0bee-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="b0bee-103">Stellt Methoden zum Abrufen von Informationen über die verwaltete Darstellung der Windows-Runtime-Typen, die derzeit in einer Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="b0bee-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="b0bee-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b0bee-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0bee-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b0bee-105">Methods</span></span>  
  
|<span data-ttu-id="b0bee-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b0bee-106">Method</span></span>|<span data-ttu-id="b0bee-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0bee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0bee-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="b0bee-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="b0bee-109">Ruft einen Enumerator für alle zwischengespeicherten Windows-Runtime-Typen ab.</span><span class="sxs-lookup"><span data-stu-id="b0bee-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="b0bee-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="b0bee-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="b0bee-111">Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne, basierend auf ihren Schnittstellenbezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="b0bee-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0bee-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0bee-112">Remarks</span></span>  
 <span data-ttu-id="b0bee-113">Diese Schnittstelle soll von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung zu verwendende `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="b0bee-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="b0bee-114">Wenn die Methode die Schnittstelle-IDs, die von einem Windows-Runtime-Server-Objekt unterstützt abruft, kann der Debugger die in der Schnittstelle definierten Methoden verwenden, sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b0bee-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="b0bee-115">Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf einer Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b0bee-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0bee-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b0bee-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bee-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0bee-117">Requirements</span></span>  
 <span data-ttu-id="b0bee-118">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="b0bee-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="b0bee-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0bee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0bee-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0bee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0bee-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0bee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bee-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0bee-122">See also</span></span>

- [<span data-ttu-id="b0bee-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b0bee-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
