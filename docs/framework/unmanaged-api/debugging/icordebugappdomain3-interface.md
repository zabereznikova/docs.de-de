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
ms.openlocfilehash: 644457edbf5035f6d946e1c83ff0053fb118288e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698233"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="a43b5-102">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a43b5-102">ICorDebugAppDomain3 Interface</span></span>

<span data-ttu-id="a43b5-103">Stellt Methoden zum Abrufen von Informationen über die verwalteten Darstellungen von Windows-Runtime Typen bereit, die derzeit in einer Anwendungsdomäne geladen sind.</span><span class="sxs-lookup"><span data-stu-id="a43b5-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="a43b5-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle und der ICorDebugAppDomain2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a43b5-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a43b5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a43b5-105">Methods</span></span>  
  
|<span data-ttu-id="a43b5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a43b5-106">Method</span></span>|<span data-ttu-id="a43b5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a43b5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a43b5-108">ICorDebugAppDomain3:: getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="a43b5-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="a43b5-109">Ruft einen Enumerator für alle zwischengespeicherten Windows-Runtime Typen ab.</span><span class="sxs-lookup"><span data-stu-id="a43b5-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="a43b5-110">ICorDebugAppDomain3:: getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="a43b5-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="a43b5-111">Ruft einen Enumerator für zwischengespeicherte Windows-Runtime Typen in einer Anwendungsdomäne auf der Grundlage ihrer Schnittstellen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="a43b5-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a43b5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a43b5-112">Remarks</span></span>  

 <span data-ttu-id="a43b5-113">Diese Schnittstelle soll von einem Debugger in Verbindung mit einem Funktions Auswertungs Aufrufe von verwendet werden `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)` .</span><span class="sxs-lookup"><span data-stu-id="a43b5-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="a43b5-114">Wenn die-Methode die von einem Windows-Runtime Server-Objekt unterstützten Schnittstellen Bezeichner abruft, verwendet der Debugger möglicherweise die in dieser Schnittstelle definierten Methoden, um Sie verwalteten Typen zuzuordnen, die diesen Schnittstellen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a43b5-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="a43b5-115">Um eine Instanz dieser Schnittstelle abzurufen, führen Sie `QueryInterface` auf einer Instanz der ICorDebugAppDomain-oder ICorDebugAppDomain2-Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="a43b5-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a43b5-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a43b5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43b5-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a43b5-117">Requirements</span></span>  

 <span data-ttu-id="a43b5-118">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="a43b5-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="a43b5-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a43b5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a43b5-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a43b5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a43b5-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a43b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43b5-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a43b5-122">See also</span></span>

- [<span data-ttu-id="a43b5-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a43b5-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
