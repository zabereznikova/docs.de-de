---
title: ICorDebugAppDomain-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: da7c0fb472df89d94fa702a13eff968a4c7e68e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785042"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="c6d90-102">ICorDebugAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d90-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="c6d90-103">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="c6d90-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="c6d90-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="c6d90-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6d90-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c6d90-105">Methods</span></span>  
  
|<span data-ttu-id="c6d90-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-106">Method</span></span>|<span data-ttu-id="c6d90-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6d90-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6d90-108">Attach-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="c6d90-109">Fügt den Debugger an die Anwendungsdomäne an.</span><span class="sxs-lookup"><span data-stu-id="c6d90-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-110">EnumerateAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="c6d90-111">Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-112">EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="c6d90-113">Ruft einen Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-114">EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="c6d90-115">Ruft einen Enumerator für alle aktiven Steppers in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-116">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="c6d90-117">Ruft die eindeutige ID der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-118">GetModuleFromMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="c6d90-119">Ruft das ICorDebug Module-Objekt mit der angegebenen Metadatenschnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="c6d90-120">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="c6d90-121">Ruft den Namen der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="c6d90-123">Ruft einen Schnittstellen Zeiger auf die Common Language Runtime (CLR)-Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="c6d90-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="c6d90-124">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="c6d90-125">Ruft den Prozess ab, der die Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="c6d90-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="c6d90-126">IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d90-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="c6d90-127">Bestimmt, ob der Debugger an die Anwendungsdomäne angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="c6d90-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d90-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6d90-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6d90-129">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c6d90-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d90-130">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6d90-130">Requirements</span></span>  
 <span data-ttu-id="c6d90-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d90-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d90-132">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d90-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d90-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d90-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d90-134">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d90-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d90-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6d90-135">See also</span></span>

- [<span data-ttu-id="c6d90-136">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c6d90-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
