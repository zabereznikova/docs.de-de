---
title: ICorDebugModule-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225637"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="1a59f-102">ICorDebugModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a59f-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="1a59f-103">Stellt ein common Language Runtime (CLR) Modul, das entweder eine ausführbare Datei oder eine Dynamic Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="1a59f-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a59f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1a59f-104">Methods</span></span>  
  
|<span data-ttu-id="1a59f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-105">Method</span></span>|<span data-ttu-id="1a59f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a59f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a59f-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="1a59f-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a59f-108">Not implemented.</span></span>|  
|[<span data-ttu-id="1a59f-109">EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="1a59f-110">Bestimmt, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a59f-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="1a59f-111">EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="1a59f-112">Bestimmt, ob der just-in-Time (JIT)-Compiler Debuginformationen für Methoden in diesem Modul werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1a59f-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="1a59f-113">GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="1a59f-114">Ruft die übergeordnete Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="1a59f-115">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="1a59f-116">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="1a59f-117">GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="1a59f-118">Ruft die ICorDebugClass aus den Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="1a59f-119">GetEditAndContinueSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="1a59f-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1a59f-120">Deprecated.</span></span>|  
|[<span data-ttu-id="1a59f-121">GetFunctionFromRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="1a59f-122">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a59f-122">Not implemented.</span></span>|  
|[<span data-ttu-id="1a59f-123">GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="1a59f-124">Ruft die Funktion, die durch das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1a59f-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="1a59f-125">GetGlobalVariableValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="1a59f-126">Ruft ein Wertobjekt für die angegebene globale Variable ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="1a59f-127">GetMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="1a59f-128">Ruft ab einen Metadaten-Schnittstellenzeiger, der verwendet werden kann, um die Metadaten für das Modul zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1a59f-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="1a59f-129">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="1a59f-130">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="1a59f-131">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="1a59f-132">Ruft die enthaltende Prozess für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="1a59f-133">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="1a59f-134">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="1a59f-135">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="1a59f-136">Ruft das Token für den Tabelleneintrag für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="1a59f-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="1a59f-137">IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="1a59f-138">Gibt an, ob das Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="1a59f-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="1a59f-139">IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="1a59f-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="1a59f-140">Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1a59f-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a59f-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a59f-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a59f-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a59f-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a59f-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a59f-143">Requirements</span></span>  
 <span data-ttu-id="1a59f-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a59f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a59f-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a59f-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a59f-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a59f-146">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1a59f-147">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1a59f-147">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a59f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a59f-148">See also</span></span>

- [<span data-ttu-id="1a59f-149">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a59f-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="1a59f-150">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1a59f-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
