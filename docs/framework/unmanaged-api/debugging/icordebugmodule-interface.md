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
ms.openlocfilehash: 86e17b48bc491c45f8b46be23ab626dc1f2a6962
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709842"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="33412-102">ICorDebugModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33412-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="33412-103">Stellt ein Common Language Runtime (CLR)-Modul dar, bei dem es sich entweder um eine ausführbare Datei oder eine DLL (Dynamic Link Library) handelt.</span><span class="sxs-lookup"><span data-stu-id="33412-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33412-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="33412-104">Methods</span></span>  
  
|<span data-ttu-id="33412-105">Methode</span><span class="sxs-lookup"><span data-stu-id="33412-105">Method</span></span>|<span data-ttu-id="33412-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33412-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33412-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="33412-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="33412-108">Not implemented.</span></span>|  
|[<span data-ttu-id="33412-109">EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="33412-110">Bestimmt, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="33412-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="33412-111">EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="33412-112">Bestimmt, ob der JIT-Compiler (Just-in-Time) Debuginformationen für Methoden in diesem Modul beibehält.</span><span class="sxs-lookup"><span data-stu-id="33412-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="33412-113">GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="33412-114">Ruft die enthaltende Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="33412-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="33412-115">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="33412-116">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="33412-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="33412-117">GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="33412-118">Ruft die ICorDebugClass aus den Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="33412-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="33412-119">GetEditAndContinueSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="33412-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="33412-120">Deprecated.</span></span>|  
|[<span data-ttu-id="33412-121">GetFunctionFromRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="33412-122">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="33412-122">Not implemented.</span></span>|  
|[<span data-ttu-id="33412-123">GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="33412-124">Ruft die Funktion ab, die vom Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="33412-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="33412-125">GetGlobalVariableValue-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="33412-126">Ruft ein Wertobjekt für die angegebene globale Variable ab.</span><span class="sxs-lookup"><span data-stu-id="33412-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="33412-127">GetMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="33412-128">Ruft einen Metadatenschnittstellen Zeiger ab, der verwendet werden kann, um die Metadaten für das Modul zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="33412-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="33412-129">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="33412-130">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="33412-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="33412-131">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="33412-132">Ruft den enthaltenden Prozess für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="33412-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="33412-133">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="33412-134">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="33412-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="33412-135">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="33412-136">Ruft das Token für den Tabelleneintrag für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="33412-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="33412-137">IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="33412-138">Gibt an, ob das Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="33412-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="33412-139">IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="33412-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="33412-140">Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="33412-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33412-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33412-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33412-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="33412-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33412-143">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="33412-143">Requirements</span></span>  

 <span data-ttu-id="33412-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33412-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33412-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33412-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33412-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33412-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33412-147">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33412-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33412-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33412-148">See also</span></span>

- [<span data-ttu-id="33412-149">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33412-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="33412-150">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="33412-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
