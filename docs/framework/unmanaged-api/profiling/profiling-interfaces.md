---
title: Profilerstellungsschnittstellen
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868147"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="85211-102">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="85211-102">Profiling Interfaces</span></span>
<span data-ttu-id="85211-103">In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die die Profilerstellung eines Programms ermöglichen, das von der Common Language Runtime (CLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85211-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85211-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="85211-104">In This Section</span></span>  
 [<span data-ttu-id="85211-105">ICLRProfiling-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="85211-106">Stellt die [attachprofiler](iclrprofiling-attachprofiler-method.md) -Methode bereit, die einem Profiler das Anfügen an einen laufenden Prozess ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="85211-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="85211-107">ICorProfilerAssemblyReferenceProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="85211-108">Ermöglicht es dem Profiler, die CLR der Assemblyverweise zu informieren, die der Profiler im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="85211-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="85211-109">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="85211-110">Stellt Methoden bereit, mit denen die CLR einen Codeprofiler benachrichtigt, wenn die abonnierten Ereignisse des Profilers auftreten.</span><span class="sxs-lookup"><span data-stu-id="85211-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="85211-111">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="85211-112">Erweitert die `ICorProfilerCallback`-Schnittstelle um Rückrufe, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85211-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="85211-113">ICorProfilerCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="85211-114">Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zum Anfüge- und Trennzustand zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="85211-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="85211-115">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="85211-116">Stellt Rückrufmethoden bereit, die von der CLR verwendet werden, um an den Profiler Informationen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="85211-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="85211-117">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="85211-118">Stellt eine Methode bereit, die den transitiven Abschluss von Objekten identifiziert, auf die durch den Garbage Collection-Stamm verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="85211-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="85211-119">ICorProfilerCallback6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="85211-120">Stellt eine Rückrufmethode bereit, die von der CLR genutzt wird, um einen Profiler zu benachrichtigen, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="85211-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="85211-121">CorProfilerCallback7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="85211-122">Stellt eine Rückruf Methode bereit, die der-Common Language Runtime verwendet, um den Profiler zu benachrichtigen, dass der mit einem in-Memory-Modul verknüpfte Symbol Datenstrom aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="85211-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="85211-123">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="85211-124">Stellt Rückruf Methoden bereit, die von der Common Language Runtime verwendet werden, um den Profiler zu benachrichtigen, dass die JIT-Kompilierung einer dynamischen Methode gestartet und beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="85211-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="85211-125">ICorProfilerCallback9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="85211-126">Stellt eine Rückruf Methode bereit, die der Common Language Runtime verwendet, um den Profiler zu benachrichtigen, dass eine dynamische Methode in eine Garbage Collection und anschließend entladen wird.</span><span class="sxs-lookup"><span data-stu-id="85211-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="85211-127">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="85211-128">Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="85211-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="85211-129">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="85211-130">Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="85211-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="85211-131">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="85211-132">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="85211-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="85211-133">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="85211-134">Erweitert die `ICorProfilerInfo`-Schnittstelle um Methoden, die in .NET Framework 2.0 und höheren Versionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85211-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="85211-135">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="85211-136">Erweitert die `ICorProfilerInfo2`-Schnittstelle um Methoden, die in der .NET Framework 4 und höheren Versionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85211-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="85211-137">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="85211-138">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="85211-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="85211-139">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="85211-140">Stellt Methoden bereit, mit denen Codeprofiler mit der CLR kommunizieren können, um die Ereignisüberwachung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="85211-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="85211-141">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="85211-142">Stellt einen Enumerator für alle Methoden bereit, die zu einem angegebenen ngen-Modul gehören und im Text einer angegebenen Methode Inline sind.</span><span class="sxs-lookup"><span data-stu-id="85211-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="85211-143">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="85211-144">Stellt eine Methode bereit, um neu definierte Metadaten auf ein Modul anzuwenden, das Zugriff auf einen in-Memory-symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="85211-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="85211-145">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="85211-146">Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="85211-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="85211-147">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="85211-148">Stellt Methoden bereit, um eine Auflistung von fixierten Objekten sequenziell zu durchlaufen, die von [Ngen. exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)generiert werden.</span><span class="sxs-lookup"><span data-stu-id="85211-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="85211-149">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="85211-150">Stellt Methoden bereit, um eine Auflistung von Threads in der CLR sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="85211-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="85211-151">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85211-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="85211-152">Stellt die [Alloc](imethodmalloc-alloc-method.md) -Methode bereit, um Arbeitsspeicher für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="85211-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="85211-153">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="85211-153">Related Sections</span></span>  
 [<span data-ttu-id="85211-154">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="85211-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="85211-155">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="85211-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="85211-156">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="85211-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="85211-157">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="85211-157">Profiling Structures</span></span>](profiling-structures.md)
