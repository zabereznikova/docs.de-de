---
title: ICorDebugAppDomain3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3
helpviewer_keywords: ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08f125d7fc388a9b2d31c9cc1cebf2605ffa7e23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="22837-102">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22837-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="22837-103">Stellt Methoden zum Abrufen von Informationen über die verwalteten Darstellungen des [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen, die derzeit in einer Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="22837-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="22837-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="22837-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22837-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="22837-105">Methods</span></span>  
  
|<span data-ttu-id="22837-106">Methode</span><span class="sxs-lookup"><span data-stu-id="22837-106">Method</span></span>|<span data-ttu-id="22837-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22837-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22837-108">Icordebugappdomain3:: Getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="22837-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="22837-109">Ruft einen Enumerator für alle zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen.</span><span class="sxs-lookup"><span data-stu-id="22837-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="22837-110">Icordebugappdomain3:: Getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="22837-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="22837-111">Ruft einen Enumerator ab, für die zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne basierend auf deren Schnittstellenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="22837-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22837-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22837-112">Remarks</span></span>  
 <span data-ttu-id="22837-113">Diese Schnittstelle von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung in verwendet werden sollen `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="22837-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="22837-114">Wenn die Methode ruft die Schnittstellenbezeichner von unterstützt ab einem [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Server-Objekt, der Debugger kann in dieser Schnittstelle definierten Methoden verwenden, um sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="22837-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="22837-115">Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf eine Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22837-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22837-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22837-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22837-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22837-117">Requirements</span></span>  
 <span data-ttu-id="22837-118">**Plattformen:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22837-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="22837-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22837-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22837-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22837-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22837-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22837-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22837-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22837-122">See Also</span></span>  
 [<span data-ttu-id="22837-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="22837-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
