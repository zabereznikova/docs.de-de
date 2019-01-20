---
title: Debugschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b6d00d17615769a5d03d58e0eda5af62ca58368
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415961"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="22962-102">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="22962-102">Debugging Interfaces</span></span>
<span data-ttu-id="22962-103">In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22962-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22962-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="22962-104">In This Section</span></span>  
 [<span data-ttu-id="22962-105">ICLRDataEnumMemoryRegions-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="22962-106">Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="22962-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="22962-107">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="22962-108">Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="22962-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="22962-109">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="22962-110">Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="22962-111">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="22962-112">Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="22962-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="22962-113">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="22962-114">Eine Unterklasse von [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , Zugriff auf Informationen über die Ausnahme bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="22962-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="22962-115">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="22962-116">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="22962-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="22962-117">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="22962-118">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) Methode, die eine Bibliotheksanbieter-Rückrufschnittstelle, die common Language Runtime versionsspezifische Debugbibliotheken abruft zu suchen und zu laden, auf Anforderung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="22962-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="22962-119">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="22962-120">Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.</span><span class="sxs-lookup"><span data-stu-id="22962-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="22962-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="22962-122">Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.</span><span class="sxs-lookup"><span data-stu-id="22962-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="22962-123">ICorDebugAppDomain-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="22962-124">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="22962-125">ICorDebugAppDomain2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="22962-126">Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="22962-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="22962-127">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22962-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="22962-128">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="22962-129">Stellt Methoden für die Arbeit mit [!INCLUDE[wrt](../../../../includes/wrt-md.md)]-Typen in einer Anwendungsdomäne bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="22962-130">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="22962-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="22962-131">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="22962-132">Erweitert logisch die [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) Schnittstelle, um ein verwaltetes Objekt über einen COM callable Wrapper abzurufen.</span><span class="sxs-lookup"><span data-stu-id="22962-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="22962-133">ICorDebugAppDomainEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="22962-134">Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="22962-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="22962-135">ICorDebugArrayValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="22962-136">Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="22962-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="22962-137">ICorDebugAssembly-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="22962-138">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="22962-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="22962-139">ICorDebugAssembly2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="22962-140">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="22962-140">Represents an assembly.</span></span> <span data-ttu-id="22962-141">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22962-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="22962-142">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="22962-143">Erweitert logisch die [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) Schnittstelle, um die Container-Assemblys und der darin enthaltenen Assemblys unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="22962-144">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-145">ICorDebugAssemblyEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="22962-146">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="22962-147">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="22962-148">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="22962-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="22962-149">ICorDebugBoxValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="22962-150">Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="22962-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="22962-151">ICorDebugBreakpoint-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="22962-152">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="22962-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="22962-153">ICorDebugBreakpointEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="22962-154">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="22962-155">ICorDebugChain-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="22962-156">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="22962-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="22962-157">ICorDebugChainEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="22962-158">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="22962-159">ICorDebugClass-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="22962-160">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="22962-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="22962-161">Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="22962-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="22962-162">ICorDebugClass2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="22962-163">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="22962-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="22962-164">Diese Schnittstelle erweitert `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="22962-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="22962-165">ICorDebugCode-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="22962-166">Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.</span><span class="sxs-lookup"><span data-stu-id="22962-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="22962-167">ICorDebugCode2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="22962-168">Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.</span><span class="sxs-lookup"><span data-stu-id="22962-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="22962-169">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="22962-170">Stellt eine Methode, die erweitert [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) und [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) um Informationen zu einem verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22962-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="22962-171">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="22962-172">Stellt eine Methode, die einen Debugger zum Aufzählen von die lokalen Variablen und Argumente in einer Funktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="22962-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="22962-173">ICorDebugCodeEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="22962-174">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="22962-175">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="22962-176">Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="22962-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="22962-177">ICorDebugContext Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="22962-178">Stellt ein Kontextobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="22962-178">Represents a context object.</span></span> <span data-ttu-id="22962-179">Diese Schnittstelle wurde noch nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="22962-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="22962-180">ICorDebugController-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="22962-181">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="22962-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="22962-182">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="22962-183">Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.</span><span class="sxs-lookup"><span data-stu-id="22962-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="22962-184">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="22962-185">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22962-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="22962-186">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-187">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="22962-188">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22962-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="22962-189">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-190">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="22962-191">Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="22962-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="22962-192">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-193">ICorDebugEditAndContinueErrorInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="22962-194">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="22962-194">Obsolete.</span></span> <span data-ttu-id="22962-195">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="22962-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="22962-196">ICorDebugEditAndContinueSnapshot-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="22962-197">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="22962-197">Obsolete.</span></span> <span data-ttu-id="22962-198">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="22962-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="22962-199">ICorDebugEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="22962-200">Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="22962-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="22962-201">ICorDebugErrorInfoEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="22962-202">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="22962-202">Obsolete.</span></span> <span data-ttu-id="22962-203">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="22962-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="22962-204">ICorDebugEval-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="22962-205">Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="22962-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="22962-206">ICorDebugEval2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="22962-207">Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="22962-208">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="22962-209">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) Schnittstelle, um die Unterstützung von Ausnahmeereignissen.</span><span class="sxs-lookup"><span data-stu-id="22962-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="22962-210">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-211">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="22962-212">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="22962-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="22962-213">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="22962-214">Erweitert die [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22962-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="22962-215">ICorDebugFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="22962-216">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="22962-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="22962-217">ICorDebugFrameEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="22962-218">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="22962-219">ICorDebugFunction-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="22962-220">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="22962-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="22962-221">ICorDebugFunction2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="22962-222">Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="22962-223">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="22962-224">Erweitert logisch die [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) Schnittstelle, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="22962-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="22962-225">ICorDebugFunctionBreakpoint-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="22962-226">Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="22962-227">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="22962-228">Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="22962-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="22962-229">ICorDebugGenericValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="22962-230">Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="22962-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="22962-231">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="22962-232">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="22962-233">Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.</span><span class="sxs-lookup"><span data-stu-id="22962-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="22962-234">ICorDebugHandleValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="22962-235">Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="22962-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="22962-236">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="22962-237">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="22962-238">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="22962-239">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="22962-240">ICorDebugHeapValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="22962-241">Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.</span><span class="sxs-lookup"><span data-stu-id="22962-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="22962-242">ICorDebugHeapValue2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="22962-243">Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.</span><span class="sxs-lookup"><span data-stu-id="22962-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="22962-244">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="22962-245">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="22962-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="22962-246">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="22962-247">Stellt ein Segment aus Intermediate Language (IL)-Code dar.</span><span class="sxs-lookup"><span data-stu-id="22962-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="22962-248">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="22962-249">Erweitert logisch die [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) -Schnittstelle um Methoden, die das Token für die lokale Variablensignatur von einer Funktion zurückgeben und, Zuordnen des Profilers instrumentierte intermediate Language (IL) offsets ursprünglichen IL-Methode versetzt.</span><span class="sxs-lookup"><span data-stu-id="22962-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="22962-250">ICorDebugILFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="22962-251">Stellt einen Stapelrahmen des MSIL-Codes dar.</span><span class="sxs-lookup"><span data-stu-id="22962-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="22962-252">ICorDebugILFrame2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="22962-253">Eine logische Erweiterung von `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="22962-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="22962-254">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="22962-255">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="22962-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="22962-256">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="22962-257">Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="22962-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="22962-258">Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="22962-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="22962-259">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="22962-260">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="22962-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="22962-261">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-262">ICorDebugInternalFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="22962-263">Identifiziert Rahmentypen für den Debugger.</span><span class="sxs-lookup"><span data-stu-id="22962-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="22962-264">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="22962-265">Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="22962-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="22962-266">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="22962-267">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-267">Provides information about a loaded module.</span></span> <span data-ttu-id="22962-268">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-269">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="22962-270">Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="22962-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="22962-271">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="22962-272">Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="22962-273">`ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="22962-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="22962-274">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="22962-275">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="22962-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="22962-276">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="22962-277">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="22962-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="22962-278">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="22962-279">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="22962-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="22962-280">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-281">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="22962-282">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="22962-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="22962-283">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-284">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="22962-285">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="22962-286">ICorDebugModule-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="22962-287">Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="22962-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="22962-288">ICorDebugModule2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="22962-289">Fungiert als logische Erweiterung von `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="22962-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="22962-290">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="22962-291">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="22962-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="22962-292">ICorDebugModuleBreakpoint-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="22962-293">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="22962-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="22962-294">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="22962-295">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung der Ereignisse auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="22962-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="22962-296">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-297">ICorDebugModuleEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="22962-298">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="22962-299">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="22962-300">Erweitert die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um änderbare Datenziele zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="22962-301">ICorDebugNativeFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="22962-302">Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22962-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="22962-303">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="22962-304">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="22962-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="22962-305">ICorDebugObjectEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="22962-306">Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.</span><span class="sxs-lookup"><span data-stu-id="22962-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="22962-307">ICorDebugObjectValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="22962-308">Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="22962-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="22962-309">ICorDebugObjectValue2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="22962-310">Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="22962-311">ICorDebugProcess-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="22962-312">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="22962-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="22962-313">ICorDebugProcess2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="22962-314">Eine logische Erweiterung von `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="22962-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="22962-315">ICorDebugProcess3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="22962-316">Steuert benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="22962-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="22962-317">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="22962-318">Erweitert die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) -Schnittstelle zur Unterstützung von Zugriff auf den verwalteten Heap, um Informationen zum Garbagecollection verwalteten Objekte bereitzustellen und zu bestimmen, ob ein Debugger Bilder aus der Anwendung lädt die lokale Cache für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="22962-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="22962-319">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="22962-320">Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle zum Aktivieren von Funktionen wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignisse und das Teilen virtueller Module codiert sind.</span><span class="sxs-lookup"><span data-stu-id="22962-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="22962-321">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-322">ICorDebugProcess7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="22962-323">Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="22962-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="22962-324">ICorDebugProcess8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="22962-325">Erweitert logisch die [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) Schnittstelle zum Aktivieren oder deaktivieren bestimmte Arten von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) ausnahmerückrufen.</span><span class="sxs-lookup"><span data-stu-id="22962-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="22962-326">ICorDebugProcessEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="22962-327">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="22962-328">ICorDebugReferenceValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="22962-329">Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="22962-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="22962-330">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="22962-331">Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22962-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="22962-332">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="22962-333">Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="22962-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="22962-334">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="22962-335">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="22962-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="22962-336">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="22962-337">Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.</span><span class="sxs-lookup"><span data-stu-id="22962-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="22962-338">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="22962-339">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="22962-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="22962-340">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="22962-341">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="22962-342">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="22962-343">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="22962-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="22962-344">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-345">ICorDebugStepper-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="22962-346">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="22962-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="22962-347">ICorDebugStepper2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="22962-348">Bietet Unterstützung für Nur mein Code-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="22962-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="22962-349">ICorDebugStepperEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="22962-350">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="22962-351">ICorDebugStringValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="22962-352">Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="22962-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="22962-353">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="22962-354">Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="22962-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="22962-355">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-356">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="22962-357">Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="22962-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="22962-358">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-359">ICorDebugThread-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="22962-360">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="22962-360">Represents a thread in a process.</span></span> <span data-ttu-id="22962-361">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="22962-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="22962-362">ICorDebugThread2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="22962-363">Fungiert als logische Erweiterung von `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="22962-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="22962-364">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="22962-365">Stellt den Einstiegspunkt für die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) und entsprechende Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="22962-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="22962-366">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="22962-367">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="22962-368">ICorDebugThreadEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="22962-369">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="22962-370">ICorDebugType-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="22962-371">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="22962-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="22962-372">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="22962-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="22962-373">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="22962-374">Erweitert die [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Schnittstelle, um die Typ-ID von einem Basistyp oder einen komplexen Typ auf (Benutzerdefiniert) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="22962-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="22962-375">ICorDebugTypeEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22962-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="22962-376">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="22962-377">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="22962-378">Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.</span><span class="sxs-lookup"><span data-stu-id="22962-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="22962-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="22962-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="22962-380">Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="22962-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="22962-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="22962-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="22962-382">Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="22962-383">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="22962-384">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="22962-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="22962-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="22962-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="22962-386">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="22962-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="22962-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="22962-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="22962-388">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="22962-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="22962-389">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="22962-390">Stellt eine lokale Variable oder ein Argument einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="22962-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="22962-391">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="22962-392">Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="22962-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="22962-393">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="22962-394">Ruft die Debugsymbolinformationen für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="22962-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="22962-395">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-396">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="22962-397">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22962-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="22962-398">**Nur .NET Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="22962-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="22962-399">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="22962-400">Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.</span><span class="sxs-lookup"><span data-stu-id="22962-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="22962-401">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="22962-402">Stellt Informationen zu einer Anwendungsdomäne dar und bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="22962-403">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="22962-404">Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="22962-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="22962-405">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="22962-406">Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="22962-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="22962-407">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="22962-408">Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.</span><span class="sxs-lookup"><span data-stu-id="22962-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="22962-409">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22962-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="22962-410">Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.</span><span class="sxs-lookup"><span data-stu-id="22962-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="22962-411">[ISOSDacInterface Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md) stellt Hilfsmethoden bereit, um den Zugriff auf Daten aus `SOS`.</span><span class="sxs-lookup"><span data-stu-id="22962-411">[ISOSDacInterface Interface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md) Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="22962-412">[IXCLRDataMethodDefinition Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md) bietet Methoden zum Abfragen von Informationen zu einer Methodendefinition.</span><span class="sxs-lookup"><span data-stu-id="22962-412">[IXCLRDataMethodDefinition Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md) Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="22962-413">[IXCLRDataMethodInstance Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md) bietet Methoden zum Abfragen von Informationen zu einer Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="22962-413">[IXCLRDataMethodInstance Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md) Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="22962-414">[IXCLRDataModule Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md) stellt Methoden zum Abfragen von Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-414">[IXCLRDataModule Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md) Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="22962-415">[IXCLRDataProcess Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md) stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="22962-415">[IXCLRDataProcess Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md) Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="22962-416">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="22962-416">Related Sections</span></span>  
 [<span data-ttu-id="22962-417">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="22962-417">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="22962-418">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="22962-418">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="22962-419">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="22962-419">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="22962-420">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="22962-420">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
