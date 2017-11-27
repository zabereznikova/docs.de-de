---
title: ICorDebugModule Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule
helpviewer_keywords: ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ced01c9c01a32468f371a8e172c878337fb79757
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="188e8-102">ICorDebugModule Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="188e8-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="188e8-103">Stellt ein common Language Runtime (CLR) Modul, das eine ausführbare Datei oder eine Dynamic Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="188e8-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="188e8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="188e8-104">Methods</span></span>  
  
|<span data-ttu-id="188e8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-105">Method</span></span>|<span data-ttu-id="188e8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="188e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="188e8-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="188e8-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="188e8-108">Not implemented.</span></span>|  
|[<span data-ttu-id="188e8-109">EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="188e8-110">Bestimmt, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="188e8-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="188e8-111">EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="188e8-112">Bestimmt, ob der Just-in-Time (JIT)-Compiler Debuginformationen für Methoden innerhalb dieses Moduls beibehält.</span><span class="sxs-lookup"><span data-stu-id="188e8-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="188e8-113">GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="188e8-114">Ruft die enthaltende Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="188e8-115">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="188e8-116">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="188e8-117">GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="188e8-118">Ruft die ICorDebugClass aus den Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="188e8-119">GetEditAndContinueSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="188e8-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="188e8-120">Deprecated.</span></span>|  
|[<span data-ttu-id="188e8-121">GetFunctionFromRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="188e8-122">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="188e8-122">Not implemented.</span></span>|  
|[<span data-ttu-id="188e8-123">GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="188e8-124">Ruft die Funktion, die durch das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="188e8-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="188e8-125">GetGlobalVariableValue-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="188e8-126">Ruft ein Wertobjekt für die angegebene globale Variable ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="188e8-127">GetMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="188e8-128">Ruft einen Schnittstellenzeiger für Metadaten, der verwendet werden kann, um die Metadaten für das Modul untersuchen.</span><span class="sxs-lookup"><span data-stu-id="188e8-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="188e8-129">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="188e8-130">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="188e8-131">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="188e8-132">Ruft den enthaltenden Prozess für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="188e8-133">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="188e8-134">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="188e8-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="188e8-135">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="188e8-136">Ruft das Token für den Tabelleneintrag für dieses Modul an.</span><span class="sxs-lookup"><span data-stu-id="188e8-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="188e8-137">IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="188e8-138">Gibt an, ob das Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="188e8-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="188e8-139">IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="188e8-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="188e8-140">Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="188e8-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="188e8-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="188e8-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="188e8-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="188e8-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="188e8-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="188e8-143">Requirements</span></span>  
 <span data-ttu-id="188e8-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="188e8-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="188e8-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="188e8-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="188e8-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="188e8-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="188e8-147">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="188e8-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188e8-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="188e8-148">See Also</span></span>  
 [<span data-ttu-id="188e8-149">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="188e8-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="188e8-150">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="188e8-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
