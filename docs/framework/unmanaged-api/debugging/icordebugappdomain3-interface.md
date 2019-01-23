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
ms.openlocfilehash: ade4c88f4431dd6db636ea2581bdb936ac8d8e5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538010"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="49df7-102">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49df7-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="49df7-103">Stellt Methoden zum Abrufen von Informationen über die verwaltete Darstellung der [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen, die derzeit in einer Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="49df7-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="49df7-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="49df7-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49df7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="49df7-105">Methods</span></span>  
  
|<span data-ttu-id="49df7-106">Methode</span><span class="sxs-lookup"><span data-stu-id="49df7-106">Method</span></span>|<span data-ttu-id="49df7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49df7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49df7-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="49df7-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="49df7-109">Ruft einen Enumerator für alle zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen.</span><span class="sxs-lookup"><span data-stu-id="49df7-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="49df7-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="49df7-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="49df7-111">Ruft einen Enumerator ab, für die Zwischenspeicherung [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne auf der Grundlage von deren Schnittstellenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="49df7-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49df7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49df7-112">Remarks</span></span>  
 <span data-ttu-id="49df7-113">Diese Schnittstelle soll von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung zu verwendende `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="49df7-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="49df7-114">Wenn die Methode ruft die Schnittstelle-IDs, die von unterstützt ab einem [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Server-Objekt, der Debugger können Sie die in der Schnittstelle definierten Methoden sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="49df7-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="49df7-115">Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf einer Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="49df7-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49df7-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="49df7-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49df7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49df7-117">Requirements</span></span>  
 <span data-ttu-id="49df7-118">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49df7-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="49df7-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49df7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49df7-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49df7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49df7-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49df7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49df7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49df7-122">See also</span></span>
- [<span data-ttu-id="49df7-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="49df7-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
