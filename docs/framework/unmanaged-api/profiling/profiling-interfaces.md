---
title: Profilerstellungsschnittstellen
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97960a43e1d7ce625d96755a7c597a0425d0911
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457461"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="137c0-102">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="137c0-102">Profiling Interfaces</span></span>
<span data-ttu-id="137c0-103">In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die die Profilerstellung eines Programms ermöglichen, das von der Common Language Runtime (CLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="137c0-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="137c0-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="137c0-104">In This Section</span></span>  
 [<span data-ttu-id="137c0-105">ICLRProfiling-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="137c0-106">Stellt die [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) -Methode, die einen Profiler an einen laufenden Prozess anfügen kann.</span><span class="sxs-lookup"><span data-stu-id="137c0-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="137c0-107">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="137c0-108">Ermöglicht es dem Profiler, um die CLR über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="137c0-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="137c0-109">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="137c0-110">Stellt Methoden bereit, mit denen die CLR einen Codeprofiler benachrichtigt, wenn die abonnierten Ereignisse des Profilers auftreten.</span><span class="sxs-lookup"><span data-stu-id="137c0-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="137c0-111">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="137c0-112">Erweitert die `ICorProfilerCallback`-Schnittstelle um Rückrufe, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="137c0-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="137c0-113">ICorProfilerCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="137c0-114">Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zum Anfüge- und Trennzustand zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="137c0-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="137c0-115">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="137c0-116">Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="137c0-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="137c0-117">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="137c0-118">Stellt eine Methode bereit, die den transitiven Abschluss von Objekten identifiziert, auf die durch den Garbage Collection-Stamm verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="137c0-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="137c0-119">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="137c0-120">Stellt eine Rückrufmethode bereit, die von der CLR genutzt wird, um einen Profiler zu benachrichtigen, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="137c0-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="137c0-121">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="137c0-122">Stellt eine Rückrufmethode, die die common Language Runtime verwendet, um den Profiler zu benachrichtigen, dass der symbolstream ein in-Memory-Modul aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="137c0-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="137c0-123">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="137c0-124">Stellt Rückrufmethoden bereit, die die common Language Runtime verwendet wird, um den Profiler zu benachrichtigen, den JIT-Kompilierung einer dynamischen Methode gestartet und abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="137c0-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="137c0-125">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="137c0-126">Stellt eine Rückrufmethode, die die common Language Runtime verwendet, um den Profiler zu benachrichtigen, den eine dynamische Methode Garbage Collector gesammelt und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="137c0-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="137c0-127">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="137c0-128">Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="137c0-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="137c0-129">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="137c0-130">Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="137c0-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="137c0-131">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="137c0-132">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="137c0-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="137c0-133">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="137c0-134">Erweitert die `ICorProfilerInfo`-Schnittstelle um Methoden, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="137c0-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="137c0-135">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="137c0-136">Erweitert die `ICorProfilerInfo2` -Schnittstelle um Methoden, die in der .NET Framework 4 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="137c0-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="137c0-137">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="137c0-138">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="137c0-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="137c0-139">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="137c0-140">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="137c0-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="137c0-141">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="137c0-142">Stellt einen Enumerator für alle Methoden, die ein bestimmtes NGen-Modul gehören, und im Text einer bestimmten Methode Inline sind.</span><span class="sxs-lookup"><span data-stu-id="137c0-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="137c0-143">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="137c0-144">Stellt eine Methode, um neu anwenden Metadaten zu einem Modul definiert und Zugriff auf eine in-Memory symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="137c0-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="137c0-145">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="137c0-146">Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="137c0-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="137c0-147">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="137c0-148">Stellt Methoden für die nacheinander durchlaufen einer Auflistung von fixierten Objekten, die vom generierten [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="137c0-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="137c0-149">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="137c0-150">Stellt Methoden bereit, um eine Auflistung von Threads in der CLR sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="137c0-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="137c0-151">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137c0-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="137c0-152">Stellt die [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) Methode zum Belegen von Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf.</span><span class="sxs-lookup"><span data-stu-id="137c0-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="137c0-153">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="137c0-153">Related Sections</span></span>  
 [<span data-ttu-id="137c0-154">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="137c0-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="137c0-155">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="137c0-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="137c0-156">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="137c0-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="137c0-157">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="137c0-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
