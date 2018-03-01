---
title: ICorDebugModule Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59c24d8305e71aac01843155b86fb54fb1e1263d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="6d24d-102">ICorDebugModule Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="6d24d-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="6d24d-103">Stellt ein common Language Runtime (CLR) Modul, das eine ausführbare Datei oder eine Dynamic Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="6d24d-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d24d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6d24d-104">Methods</span></span>  
  
|<span data-ttu-id="6d24d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-105">Method</span></span>|<span data-ttu-id="6d24d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d24d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d24d-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="6d24d-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="6d24d-108">Not implemented.</span></span>|  
|[<span data-ttu-id="6d24d-109">EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="6d24d-110">Bestimmt, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6d24d-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="6d24d-111">EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="6d24d-112">Bestimmt, ob der Just-in-Time (JIT)-Compiler Debuginformationen für Methoden innerhalb dieses Moduls beibehält.</span><span class="sxs-lookup"><span data-stu-id="6d24d-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="6d24d-113">GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="6d24d-114">Ruft die enthaltende Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="6d24d-115">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="6d24d-116">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="6d24d-117">GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="6d24d-118">Ruft die ICorDebugClass aus den Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="6d24d-119">GetEditAndContinueSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="6d24d-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="6d24d-120">Deprecated.</span></span>|  
|[<span data-ttu-id="6d24d-121">GetFunctionFromRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="6d24d-122">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="6d24d-122">Not implemented.</span></span>|  
|[<span data-ttu-id="6d24d-123">GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="6d24d-124">Ruft die Funktion, die durch das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6d24d-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="6d24d-125">GetGlobalVariableValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="6d24d-126">Ruft ein Wertobjekt für die angegebene globale Variable ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="6d24d-127">GetMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="6d24d-128">Ruft einen Schnittstellenzeiger für Metadaten, der verwendet werden kann, um die Metadaten für das Modul untersuchen.</span><span class="sxs-lookup"><span data-stu-id="6d24d-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="6d24d-129">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="6d24d-130">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="6d24d-131">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="6d24d-132">Ruft den enthaltenden Prozess für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="6d24d-133">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="6d24d-134">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="6d24d-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="6d24d-135">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="6d24d-136">Ruft das Token für den Tabelleneintrag für dieses Modul an.</span><span class="sxs-lookup"><span data-stu-id="6d24d-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="6d24d-137">IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="6d24d-138">Gibt an, ob das Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="6d24d-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="6d24d-139">IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="6d24d-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="6d24d-140">Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d24d-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d24d-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d24d-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d24d-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6d24d-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d24d-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d24d-143">Requirements</span></span>  
 <span data-ttu-id="6d24d-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d24d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d24d-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d24d-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d24d-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d24d-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d24d-147">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d24d-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d24d-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d24d-148">See Also</span></span>  
 [<span data-ttu-id="6d24d-149">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d24d-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="6d24d-150">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6d24d-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
