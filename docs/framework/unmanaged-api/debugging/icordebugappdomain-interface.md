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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12753ab65f9339e8f6c3049bb72755e87464eb1a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963111"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="58102-102">ICorDebugAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58102-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="58102-103">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="58102-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="58102-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="58102-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58102-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="58102-105">Methods</span></span>  
  
|<span data-ttu-id="58102-106">Methode</span><span class="sxs-lookup"><span data-stu-id="58102-106">Method</span></span>|<span data-ttu-id="58102-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58102-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58102-108">Attach-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="58102-109">Fügt den Debugger an die Anwendungsdomäne an.</span><span class="sxs-lookup"><span data-stu-id="58102-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="58102-110">EnumerateAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="58102-111">Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="58102-112">EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="58102-113">Ruft einen Enumerator für alle aktiven Breakpoints in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="58102-114">EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="58102-115">Ruft einen Enumerator für alle aktiven Steppers in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="58102-116">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="58102-117">Ruft die eindeutige ID der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="58102-118">GetModuleFromMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="58102-119">Ruft das ICorDebug Module-Objekt mit der angegebenen Metadatenschnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="58102-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="58102-120">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="58102-121">Ruft den Namen der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="58102-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="58102-123">Ruft einen Schnittstellen Zeiger auf die Common Language Runtime (CLR)-Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="58102-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="58102-124">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="58102-125">Ruft den Prozess ab, der die Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="58102-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="58102-126">IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="58102-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="58102-127">Bestimmt, ob der Debugger an die Anwendungsdomäne angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="58102-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58102-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58102-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58102-129">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58102-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58102-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58102-130">Requirements</span></span>  
 <span data-ttu-id="58102-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58102-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58102-132">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="58102-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58102-133">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58102-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58102-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58102-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58102-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58102-135">See also</span></span>

- [<span data-ttu-id="58102-136">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="58102-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
