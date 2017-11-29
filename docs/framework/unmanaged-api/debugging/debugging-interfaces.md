---
title: Debugschnittstellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de2469d15eef40b9ef283d67aeca429d9d96a7ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-interfaces"></a><span data-ttu-id="1effa-102">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1effa-102">Debugging Interfaces</span></span>
<span data-ttu-id="1effa-103">In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1effa-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1effa-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1effa-104">In This Section</span></span>  
 [<span data-ttu-id="1effa-105">ICLRDataEnumMemoryRegions-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="1effa-106">Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1effa-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="1effa-107">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="1effa-108">Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="1effa-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="1effa-109">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="1effa-110">Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="1effa-111">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="1effa-112">Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="1effa-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="1effa-113">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="1effa-114">Eine Unterklasse von [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , Zugriff auf Ausnahmeinformationen bietet.</span><span class="sxs-lookup"><span data-stu-id="1effa-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="1effa-115">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="1effa-116">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="1effa-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="1effa-117">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="1effa-118">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) -Methode, die eine Bibliotheksanbieter Rückrufschnittstelle abruft, die common Language Runtime versionsspezifische befindet, und Laden bei Bedarf es ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1effa-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="1effa-119">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="1effa-120">Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.</span><span class="sxs-lookup"><span data-stu-id="1effa-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="1effa-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="1effa-122">Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.</span><span class="sxs-lookup"><span data-stu-id="1effa-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="1effa-123">ICorDebugAppDomain Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="1effa-124">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="1effa-125">ICorDebugAppDomain2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="1effa-126">Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1effa-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="1effa-127">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1effa-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="1effa-128">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="1effa-129">Stellt Methoden für die Arbeit mit [!INCLUDE[wrt](../../../../includes/wrt-md.md)]-Typen in einer Anwendungsdomäne bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="1effa-130">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1effa-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="1effa-131">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="1effa-132">Erweitert logisch die [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) Schnittstelle, um ein verwaltetes Objekt aus einen aufrufbaren COM-Wrapper abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1effa-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="1effa-133">ICorDebugAppDomainEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="1effa-134">Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1effa-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="1effa-135">ICorDebugArrayValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="1effa-136">Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="1effa-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="1effa-137">ICorDebugAssembly Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="1effa-138">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="1effa-139">ICorDebugAssembly2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="1effa-140">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-140">Represents an assembly.</span></span> <span data-ttu-id="1effa-141">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1effa-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="1effa-142">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="1effa-143">Erweitert logisch die [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) -Schnittstelle zur Unterstützung für Container Assemblys und der darin enthaltenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="1effa-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="1effa-144">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-145">ICorDebugAssemblyEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="1effa-146">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-147">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="1effa-148">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="1effa-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="1effa-149">ICorDebugBoxValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="1effa-150">Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1effa-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="1effa-151">ICorDebugBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="1effa-152">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="1effa-153">ICorDebugBreakpointEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="1effa-154">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-155">ICorDebugChain Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="1effa-156">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="1effa-157">ICorDebugChainEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="1effa-158">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-159">ICorDebugClass Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="1effa-160">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="1effa-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1effa-161">Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="1effa-162">ICorDebugClass2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="1effa-163">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1effa-164">Diese Schnittstelle erweitert `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="1effa-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="1effa-165">ICorDebugCode Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="1effa-166">Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="1effa-167">ICorDebugCode2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="1effa-168">Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.</span><span class="sxs-lookup"><span data-stu-id="1effa-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="1effa-169">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="1effa-170">Stellt eine Methode, die erweitert [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) und [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) um Informationen zu einem verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1effa-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="1effa-171">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="1effa-172">Stellt eine Methode, die einen Debugger zum Auflisten der lokale Variablen und Argumente in einer Funktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1effa-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="1effa-173">ICorDebugCodeEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="1effa-174">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-175">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="1effa-176">Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1effa-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="1effa-177">ICorDebugContext Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="1effa-178">Stellt ein Kontextobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-178">Represents a context object.</span></span> <span data-ttu-id="1effa-179">Diese Schnittstelle wurde noch nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1effa-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="1effa-180">ICorDebugController Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="1effa-181">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1effa-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="1effa-182">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="1effa-183">Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.</span><span class="sxs-lookup"><span data-stu-id="1effa-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="1effa-184">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="1effa-185">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1effa-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="1effa-186">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-187">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="1effa-188">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1effa-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="1effa-189">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-190">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="1effa-191">Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1effa-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="1effa-192">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-193">ICorDebugEditAndContinueErrorInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="1effa-194">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1effa-194">Obsolete.</span></span> <span data-ttu-id="1effa-195">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1effa-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="1effa-196">ICorDebugEditAndContinueSnapshot Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="1effa-197">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1effa-197">Obsolete.</span></span> <span data-ttu-id="1effa-198">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1effa-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="1effa-199">ICorDebugEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="1effa-200">Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="1effa-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="1effa-201">ICorDebugErrorInfoEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="1effa-202">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1effa-202">Obsolete.</span></span> <span data-ttu-id="1effa-203">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1effa-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="1effa-204">ICorDebugEval Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="1effa-205">Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1effa-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="1effa-206">ICorDebugEval2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="1effa-207">Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="1effa-208">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="1effa-209">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) Schnittstelle, um die Unterstützung von Ausnahmeereignissen.</span><span class="sxs-lookup"><span data-stu-id="1effa-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="1effa-210">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-211">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="1effa-212">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="1effa-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="1effa-213">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="1effa-214">Erweitert die [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1effa-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="1effa-215">ICorDebugFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="1effa-216">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="1effa-217">ICorDebugFrameEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="1effa-218">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-219">ICorDebugFunction Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="1effa-220">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="1effa-221">ICorDebugFunction2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="1effa-222">Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="1effa-223">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="1effa-224">Erweitert logisch die [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) Schnittstelle, um den Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="1effa-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="1effa-225">ICorDebugFunctionBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="1effa-226">Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="1effa-227">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="1effa-228">Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1effa-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="1effa-229">ICorDebugGenericValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="1effa-230">Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="1effa-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="1effa-231">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="1effa-232">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="1effa-233">Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.</span><span class="sxs-lookup"><span data-stu-id="1effa-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="1effa-234">ICorDebugHandleValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="1effa-235">Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="1effa-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="1effa-236">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="1effa-237">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="1effa-238">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="1effa-239">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="1effa-240">ICorDebugHeapValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="1effa-241">Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1effa-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="1effa-242">ICorDebugHeapValue2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="1effa-243">Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1effa-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="1effa-244">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="1effa-245">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1effa-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="1effa-246">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="1effa-247">Stellt ein Segment aus Intermediate Language (IL)-Code dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="1effa-248">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="1effa-249">Erweitert logisch die [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) -Schnittstelle um Methoden, die das Token für die lokale Variablensignatur einer Funktion zurückgeben und, Zuordnen eines Profilers den instrumentierte intermediate Language (IL) an die ursprüngliche Methode IL-offsets UTC-Offsets.</span><span class="sxs-lookup"><span data-stu-id="1effa-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="1effa-250">ICorDebugILFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="1effa-251">Stellt einen Stapelrahmen des MSIL-Codes dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="1effa-252">ICorDebugILFrame2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="1effa-253">Eine logische Erweiterung von `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="1effa-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="1effa-254">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="1effa-255">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="1effa-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="1effa-256">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="1effa-257">Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1effa-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="1effa-258">Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1effa-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="1effa-259">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="1effa-260">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="1effa-261">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-262">ICorDebugInternalFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="1effa-263">Identifiziert Rahmentypen für den Debugger.</span><span class="sxs-lookup"><span data-stu-id="1effa-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="1effa-264">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="1effa-265">Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="1effa-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="1effa-266">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="1effa-267">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-267">Provides information about a loaded module.</span></span> <span data-ttu-id="1effa-268">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-269">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="1effa-270">Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1effa-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="1effa-271">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="1effa-272">Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="1effa-273">`ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="1effa-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="1effa-274">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="1effa-275">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1effa-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="1effa-276">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="1effa-277">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="1effa-278">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="1effa-279">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="1effa-280">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-281">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="1effa-282">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="1effa-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="1effa-283">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-284">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="1effa-285">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="1effa-286">ICorDebugModule Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="1effa-287">Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="1effa-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="1effa-288">ICorDebugModule2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="1effa-289">Fungiert als logische Erweiterung von `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="1effa-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="1effa-290">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="1effa-291">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="1effa-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="1effa-292">ICorDebugModuleBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="1effa-293">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1effa-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="1effa-294">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="1effa-295">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung der Ereignisse auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="1effa-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="1effa-296">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-297">ICorDebugModuleEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="1effa-298">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-299">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="1effa-300">Erweitert die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um änderbare Datenziele zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="1effa-301">ICorDebugNativeFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="1effa-302">Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1effa-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="1effa-303">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="1effa-304">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1effa-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="1effa-305">ICorDebugObjectEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="1effa-306">Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="1effa-307">ICorDebugObjectValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="1effa-308">Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1effa-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="1effa-309">ICorDebugObjectValue2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="1effa-310">Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="1effa-311">ICorDebugProcess Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="1effa-312">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="1effa-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="1effa-313">ICorDebugProcess2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="1effa-314">Eine logische Erweiterung von `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="1effa-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="1effa-315">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="1effa-316">Steuert benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="1effa-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="1effa-317">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="1effa-318">Erweitert die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) -Schnittstelle zur Unterstützung der Zugriff auf den verwalteten Heap an, um Informationen zum Garbagecollection verwalteten Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus der Anwendung lädt der lokalen Cache für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="1effa-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="1effa-319">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="1effa-320">Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignissen und Teilen virtueller Module codiert sind.</span><span class="sxs-lookup"><span data-stu-id="1effa-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="1effa-321">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-322">ICorDebugProcess7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="1effa-323">Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1effa-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="1effa-324">ICorDebugProcess8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="1effa-325">Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) ausnahmerückrufen.</span><span class="sxs-lookup"><span data-stu-id="1effa-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="1effa-326">ICorDebugProcessEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="1effa-327">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-328">ICorDebugReferenceValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="1effa-329">Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1effa-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="1effa-330">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="1effa-331">Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1effa-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="1effa-332">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="1effa-333">Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="1effa-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="1effa-334">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="1effa-335">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="1effa-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="1effa-336">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="1effa-337">Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.</span><span class="sxs-lookup"><span data-stu-id="1effa-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="1effa-338">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="1effa-339">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="1effa-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="1effa-340">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="1effa-341">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="1effa-342">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="1effa-343">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="1effa-344">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-345">ICorDebugStepper Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="1effa-346">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="1effa-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="1effa-347">ICorDebugStepper2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="1effa-348">Bietet Unterstützung für Nur mein Code-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="1effa-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="1effa-349">ICorDebugStepperEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="1effa-350">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-351">ICorDebugStringValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="1effa-352">Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="1effa-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="1effa-353">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="1effa-354">Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1effa-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="1effa-355">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-356">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="1effa-357">Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1effa-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="1effa-358">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-359">ICorDebugThread Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="1effa-360">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-360">Represents a thread in a process.</span></span> <span data-ttu-id="1effa-361">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="1effa-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="1effa-362">ICorDebugThread2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="1effa-363">Fungiert als logische Erweiterung von `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="1effa-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="1effa-364">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="1effa-365">Stellt den Einstiegspunkt für die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) und entsprechende Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1effa-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="1effa-366">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="1effa-367">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="1effa-368">ICorDebugThreadEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="1effa-369">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-370">ICorDebugType Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="1effa-371">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="1effa-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1effa-372">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1effa-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="1effa-373">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="1effa-374">Erweitert die [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Schnittstelle, um die Typ-ID von einem Basistyp oder komplexen (Benutzerdefiniert) Typ abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1effa-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="1effa-375">ICorDebugTypeEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1effa-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="1effa-376">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-377">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="1effa-378">Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.</span><span class="sxs-lookup"><span data-stu-id="1effa-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="1effa-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="1effa-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="1effa-380">Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="1effa-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="1effa-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="1effa-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="1effa-382">Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="1effa-383">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="1effa-384">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="1effa-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="1effa-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="1effa-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="1effa-386">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1effa-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="1effa-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="1effa-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="1effa-388">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1effa-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="1effa-389">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="1effa-390">Stellt eine lokale Variable oder ein Argument einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="1effa-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="1effa-391">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="1effa-392">Stellt einen Enumerator an lokale Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="1effa-393">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="1effa-394">Ruft die Debugsymbolinformationen für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="1effa-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="1effa-395">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-396">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="1effa-397">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1effa-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="1effa-398">**Nur für .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1effa-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="1effa-399">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="1effa-400">Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.</span><span class="sxs-lookup"><span data-stu-id="1effa-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="1effa-401">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="1effa-402">Stellt Informationen zu einer Anwendungsdomäne dar und bereit.</span><span class="sxs-lookup"><span data-stu-id="1effa-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="1effa-403">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="1effa-404">Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1effa-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="1effa-405">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="1effa-406">Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="1effa-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="1effa-407">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="1effa-408">Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1effa-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="1effa-409">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1effa-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="1effa-410">Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.</span><span class="sxs-lookup"><span data-stu-id="1effa-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1effa-411">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1effa-411">Related Sections</span></span>  
 [<span data-ttu-id="1effa-412">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="1effa-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="1effa-413">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="1effa-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="1effa-414">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="1effa-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="1effa-415">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="1effa-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
