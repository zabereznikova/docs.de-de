---
title: .NET-Glossar
description: "Informationen zu den Bedeutungen der ausgewählten Begriffe, die in der .NET-Dokumentation verwendet werden."
keywords: ".NET-Glossar, .NET-Wörterbuch, .NET-Terminologie, .NET-Plattform, .NET-Framework, .NET-Runtime"
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33123732514a53574036f6f8e948b2cf9acb9229
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="net-glossary"></a><span data-ttu-id="00477-104">.NET-Glossar</span><span class="sxs-lookup"><span data-stu-id="00477-104">.NET Glossary</span></span>

<span data-ttu-id="00477-105">Der primäre Zweck dieses Glossars ist die Klärung der Bedeutungen der ausgewählten Begriffe und Akronyme, die häufig ohne Definitionen in der .NET-Dokumentation auftauchen.</span><span class="sxs-lookup"><span data-stu-id="00477-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="00477-106">AOT</span><span class="sxs-lookup"><span data-stu-id="00477-106">AOT</span></span>

<span data-ttu-id="00477-107">Ahead-of-Time-Compiler</span><span class="sxs-lookup"><span data-stu-id="00477-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="00477-108">Ähnlich wie bei [JIT](#jit) übersetzt dieser Compiler ebenfalls [IL](#il) in Computercode.</span><span class="sxs-lookup"><span data-stu-id="00477-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="00477-109">Im Gegensatz zur JIT-Kompilierung erfolgt die AOT-Kompilierung, bevor die Anwendung ausgeführt wird und wird von einem anderen Computer aus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="00477-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="00477-110">Da AOT-Toolketten nicht während der Laufzeit kompiliert werden, muss die Zeit, die für das Kompilieren aufgewendet wird, nicht minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="00477-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="00477-111">Das bedeutet, dass mehr Zeit in die Optimierung investiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="00477-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="00477-112">Da die gesamte Anwendung den Kontext der AOT darstellt, führt der AOT-Compiler auch modulübergreifende Verknüpfungen und die Analyse des gesamten Programms aus. Das bedeutet, dass allen Verweisen gefolgt und eine einzige ausführbare Datei generiert wird.</span><span class="sxs-lookup"><span data-stu-id="00477-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="00477-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00477-113">ASP.NET</span></span> 

<span data-ttu-id="00477-114">Die ursprüngliche ASP.NET-Implementierung, die im Lieferumfang von .NET Framework enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="00477-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="00477-115">Bei ASP.NET handelt es sich manchmal um einen Oberbegriff, der sich auf ASP.NET-Implementierungen, einschließlich ASP.NET Core, bezieht.</span><span class="sxs-lookup"><span data-stu-id="00477-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="00477-116">Die Bedeutung des Begriffs in einer bestimmten Instanz wird durch den Kontext festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00477-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="00477-117">Beziehen Sie sich auf ASP.NET 4.x, wenn Sie klarstellen möchten, dass Sie ASP.NET nicht für beide Implementierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="00477-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="00477-118">Siehe [ASP.NET-Dokumentation](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="00477-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="00477-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00477-119">ASP.NET Core</span></span>

<span data-ttu-id="00477-120">Eine plattformübergreifende, leistungsstarke Open Source-Implementierung von ASP.NET, die auf .NET Core basiert.</span><span class="sxs-lookup"><span data-stu-id="00477-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="00477-121">Siehe [ASP.NET Core-Dokumentation](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="00477-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="00477-122">Assembly</span><span class="sxs-lookup"><span data-stu-id="00477-122">assembly</span></span>

<span data-ttu-id="00477-123">Eine *.dll*/*.exe*-Datei, die eine Sammlung von APIs enthält, die von Apps oder anderen Assemblys aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="00477-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="00477-124">Eine Assembly kann Typen wie Schnittstellen, Klassen, Strukturen, Enumerationen und Delegaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="00477-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="00477-125">Assemblys im Ordner *bin* eines Projekts werden manchmal als *Binärdateien* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="00477-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="00477-126">Siehe auch [Bibliotheken](#library).</span><span class="sxs-lookup"><span data-stu-id="00477-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="00477-127">CLR</span><span class="sxs-lookup"><span data-stu-id="00477-127">CLR</span></span>

<span data-ttu-id="00477-128">Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="00477-128">Common Language Runtime.</span></span>

<span data-ttu-id="00477-129">Die genaue Bedeutung hängt vom Kontext ab, normalerweise wird damit jedoch die Runtime des .NET Framework bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="00477-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="00477-130">Die CLR behandelt die Speicherbelegung und -verwaltung.</span><span class="sxs-lookup"><span data-stu-id="00477-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="00477-131">Bei der CLR handelt es sich auch um einen virtuellen Computer, der nicht nur Apps ausführt, sondern auch mithilfe eines JIT-Compilers dynamisch Code generiert und kompiliert.</span><span class="sxs-lookup"><span data-stu-id="00477-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="00477-132">Die aktuelle Microsoft CLR-Implementierung ist nur unter Windows möglich.</span><span class="sxs-lookup"><span data-stu-id="00477-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="00477-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="00477-133">CoreCLR</span></span>

<span data-ttu-id="00477-134">.NET Core Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="00477-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="00477-135">Die CoreCLR basiert auf demselben Code wie die CLR.</span><span class="sxs-lookup"><span data-stu-id="00477-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="00477-136">rsprünglich war CoreCLR die Runtime von Silverlight und wurde entworfen, um auf mehreren Plattformen ausgeführt zu werden, besonders unter Windows und OS X. CoreCLR ist nun Teil von .NET Core und stellt eine vereinfachte Version der CLR dar.</span><span class="sxs-lookup"><span data-stu-id="00477-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="00477-137">Es handelt sich dabei immer noch um eine plattformübergreifende Runtime, die nun viele Linux-Verteilungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="00477-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="00477-138">CoreCLR ist auch ein virtueller Computer mit JIT und Funktionen für die Codeausführung.</span><span class="sxs-lookup"><span data-stu-id="00477-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="00477-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="00477-139">CoreFX</span></span>

<span data-ttu-id="00477-140">.NET Core-Basisklassenbibliothek (BCL)</span><span class="sxs-lookup"><span data-stu-id="00477-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="00477-141">Eine Reihe von Bibliotheken, aus denen die Systemnamespaces (und in beschränktem Umfang die Microsoft-Namespaces) bestehen.</span><span class="sxs-lookup"><span data-stu-id="00477-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="00477-142">Bei der BCL handelt es sich um ein allgemeines Framework auf niedriger Ebene, auf dem Anwendungsframeworks auf höherer Ebene, z.B. ASP.NET Core, basieren.</span><span class="sxs-lookup"><span data-stu-id="00477-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="00477-143">Der Quellcode der .NET Core-BCL ist im [CoreFX-Repository](https://github.com/dotnet/corefx) enthalten.</span><span class="sxs-lookup"><span data-stu-id="00477-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="00477-144">Der Großteil der .NET Core-APIs ist jedoch auch im .NET Framework verfügbar, sodass Sie sich CoreFX als einen Fork der .NET Framework-BCL vorstellen können.</span><span class="sxs-lookup"><span data-stu-id="00477-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="00477-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="00477-145">CoreRT</span></span>

<span data-ttu-id="00477-146">.NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="00477-146">.NET Core runtime.</span></span>

<span data-ttu-id="00477-147">Im Gegensatz zu CLR und CoreCLR handelt es sich bei CoreRT nicht um einen virtuellen Computer. Das bedeutet, dass die Funktionen zum dynamischen Generieren und Ausführen von Code nicht enthalten sind, da kein [JIT](#jit) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="00477-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="00477-148">Es ist jedoch ein [GC](#gc) enthalten sowie die Möglichkeit zur Identifikation und Reflektion des Laufzeittyps (RTTI).</span><span class="sxs-lookup"><span data-stu-id="00477-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="00477-149">Das Typsystem wurde jedoch so entwickelt, dass keine Metadaten für die Reflektion erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="00477-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="00477-150">Dadurch wird eine [AOT](#aot)-Toolkette ermöglicht, die die Verknüpfung zu überflüssigen Metadaten aufheben und (was noch wichtiger ist) Code identifizieren kann, der von der App nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00477-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="00477-151">CoreRT befindet sich in der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="00477-151">CoreRT is in development.</span></span>

<span data-ttu-id="00477-152">Siehe [Intro to .NET Native and CoreRT (Einführung in .NET Native und CoreRT)](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="00477-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="00477-153">Umgebung</span><span class="sxs-lookup"><span data-stu-id="00477-153">ecosystem</span></span>

<span data-ttu-id="00477-154">Jede Laufzeitsoftware und alle Entwicklungstools und Communityressourcen, die zum Erstellen und Ausführen von Anwendungen für eine bestimmte Technologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00477-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="00477-155">Der Begriff „.NET-Umgebung“ unterscheidet sich von ähnlichen Begriffen wie „.NET-Stapel“ durch seine Einbindung von Apps und Bibliotheken, die von Drittanbietern stammen.</span><span class="sxs-lookup"><span data-stu-id="00477-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="00477-156">Hier ein Beispiel in einem Satz:</span><span class="sxs-lookup"><span data-stu-id="00477-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="00477-157">„Die Motivation hinter [.NET Standard](#net-standard) ist das Herstellen einer umfassenderen Einheitlichkeit in der .NET-Umgebung.“</span><span class="sxs-lookup"><span data-stu-id="00477-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="00477-158">Framework</span><span class="sxs-lookup"><span data-stu-id="00477-158">framework</span></span>

<span data-ttu-id="00477-159">Allgemein handelt es sich dabei um eine umfassende Sammlung von APIs, die die Entwicklung und Bereitstellung von Anwendungen erleichtert, die auf einer bestimmten Technologie basieren.</span><span class="sxs-lookup"><span data-stu-id="00477-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="00477-160">Allgemein sind ASP.NET Core und Windows Forms Beispiele für Anwendungsframeworks.</span><span class="sxs-lookup"><span data-stu-id="00477-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="00477-161">Siehe auch [Bibliotheken](#library).</span><span class="sxs-lookup"><span data-stu-id="00477-161">See also [library](#library).</span></span>

<span data-ttu-id="00477-162">Das Wort „Framework“ hat in den folgenden Begriffen eine spezifischere technische Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="00477-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="00477-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="00477-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="00477-164">Zielframework</span><span class="sxs-lookup"><span data-stu-id="00477-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="00477-165">TFM (Zielframeworkmoniker)</span><span class="sxs-lookup"><span data-stu-id="00477-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="00477-166">In der bestehenden Dokumentation bezieht sich „Framework“ manchmal auf eine [Implementierung von .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="00477-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="00477-167">In einem Artikel kann .NET Core beispielsweise als Framework bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="00477-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="00477-168">Diese verwirrende Verwendung soll aus der Dokumentation beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="00477-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="00477-169">GC</span><span class="sxs-lookup"><span data-stu-id="00477-169">GC</span></span>

<span data-ttu-id="00477-170">Garbage Collector</span><span class="sxs-lookup"><span data-stu-id="00477-170">Garbage collector.</span></span>

<span data-ttu-id="00477-171">Der Garbage Collector ist eine Implementierung der automatischen Speicherverwaltung.</span><span class="sxs-lookup"><span data-stu-id="00477-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="00477-172">Der GC gibt Arbeitsspeicher frei, der durch Objekte belegt ist, die nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00477-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="00477-173">Siehe [Garbage Collection](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="00477-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="00477-174">IL</span><span class="sxs-lookup"><span data-stu-id="00477-174">IL</span></span>

<span data-ttu-id="00477-175">Zwischensprache</span><span class="sxs-lookup"><span data-stu-id="00477-175">Intermediate language.</span></span>

<span data-ttu-id="00477-176">.NET-Sprachen auf höherer Ebene, z.B. C#, werden zu einem hardwareunabhängigen Anweisungssatz kompiliert, der als Zwischensprache (Intermediate Language, IL) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="00477-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="00477-177">IL wird manchmal als MSIL (Microsoft IL) oder CIL (Common IL) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="00477-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="00477-178">JIT</span><span class="sxs-lookup"><span data-stu-id="00477-178">JIT</span></span>

<span data-ttu-id="00477-179">Just-In-Time-Compiler</span><span class="sxs-lookup"><span data-stu-id="00477-179">Just-in-time compiler.</span></span>

<span data-ttu-id="00477-180">Ähnlich wie bei [AOT](#aot) übersetzt dieser Compiler [IL](#il) in einen Computercode, den der Prozessor versteht.</span><span class="sxs-lookup"><span data-stu-id="00477-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="00477-181">Im Gegensatz zu AOT erfolgt die JIT-Kompilierung bei Bedarf und wird vom selben Computer aus ausgeführt, auf dem auch der Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="00477-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="00477-182">Da die JIT-Kompilierung während der Ausführung der Anwendung stattfindet, ist die Kompilierzeit Teil der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="00477-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="00477-183">Daher müssen JIT-Compiler eine Balance zwischen der Zeit, die in die Optimierung des Codes investiert werden kann, und den Ersparnissen, die der resultierende Code erzeugt, finden.</span><span class="sxs-lookup"><span data-stu-id="00477-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="00477-184">Ein JIT kennt jedoch die tatsächliche Hardware und befreit die Entwickler davon, verschiedene Implementierungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="00477-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="00477-185">Implementierung von .NET</span><span class="sxs-lookup"><span data-stu-id="00477-185">implementation of .NET</span></span>

<span data-ttu-id="00477-186">Eine Implementierung von .NET umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="00477-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="00477-187">Mindestens eine Runtime.</span><span class="sxs-lookup"><span data-stu-id="00477-187">One or more runtimes.</span></span> <span data-ttu-id="00477-188">Beispiele: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="00477-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="00477-189">Eine Klassenbibliothek, die eine Version des .NET Standards implementiert und ggf. zusätzliche APIs beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="00477-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="00477-190">Beispiele: .NET Framework-Basisklassenbibliothek, .NET Core-Basisklassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="00477-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="00477-191">Optional mindestens ein Anwendungsframework.</span><span class="sxs-lookup"><span data-stu-id="00477-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="00477-192">Beispiele: ASP.NET, Windows Forms und WPF sind in .NET Framework enthalten.</span><span class="sxs-lookup"><span data-stu-id="00477-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="00477-193">Optional Entwicklungstools.</span><span class="sxs-lookup"><span data-stu-id="00477-193">Optionally, development tools.</span></span> <span data-ttu-id="00477-194">Einige Entwicklungstools werden zwischen mehreren Implementierungen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="00477-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="00477-195">Beispiele für .NET-Implementierungen:</span><span class="sxs-lookup"><span data-stu-id="00477-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="00477-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="00477-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="00477-197">.NET Core</span><span class="sxs-lookup"><span data-stu-id="00477-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="00477-198">Universelle Windows-Plattform (UWP)</span><span class="sxs-lookup"><span data-stu-id="00477-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="00477-199">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="00477-199">library</span></span>

<span data-ttu-id="00477-200">Eine Sammlung von APIs, die durch Apps oder andere Bibliotheken aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="00477-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="00477-201">Eine .NET-Bibliothek besteht aus einer oder mehreren [Assemblys](#assembly).</span><span class="sxs-lookup"><span data-stu-id="00477-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="00477-202">Die Wörter „Bibliothek“ und [Framework](#framework) werden häufig synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="00477-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="00477-203">Metapaket</span><span class="sxs-lookup"><span data-stu-id="00477-203">metapackage</span></span>

<span data-ttu-id="00477-204">Ein NuGet-Paket, das über keine eigene Bibliothek verfügt, sondern nur eine Liste der Abhängigkeiten darstellt.</span><span class="sxs-lookup"><span data-stu-id="00477-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="00477-205">Die enthaltenen Pakete können optional die API für ein Zielframework erzeugen.</span><span class="sxs-lookup"><span data-stu-id="00477-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="00477-206">Siehe [Pakete, Metapakete und Frameworks](../core/packages.md).</span><span class="sxs-lookup"><span data-stu-id="00477-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="00477-207">Mono</span><span class="sxs-lookup"><span data-stu-id="00477-207">Mono</span></span>

<span data-ttu-id="00477-208">Bei Mono handelt es sich um eine .NET-Implementierung, die in erster Linie verwendet wird, wenn eine kleine Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="00477-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="00477-209">Mono ist die Runtime für Xamarin-Anwendungen unter Android, Mac, iOS, tvOS und watchOS und ist hauptsächlich auf Apps mit geringem Ressourcenbedarf ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="00477-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="00477-210">Außerdem unterstützt Mono alle derzeit veröffentlichten Versionen des .NET Standards.</span><span class="sxs-lookup"><span data-stu-id="00477-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="00477-211">In der Vergangenheit hat Mono die größere API des .NET Framework implementiert und einige der beliebtesten Funktionen unter Unix emuliert.</span><span class="sxs-lookup"><span data-stu-id="00477-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="00477-212">Manchmal wird es zum Ausführen von .NET-Anwendungen verwendet, die auf diesen Unix-Funktionen basieren.</span><span class="sxs-lookup"><span data-stu-id="00477-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="00477-213">Mono wird in der Regel mit einem Just-In-Time-Compiler verwendet. Es enthält aber auch einen vollständig statischen Compiler (Ahead-of-time-Kompilierung), der auf Plattformen wie iOS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00477-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="00477-214">Weitere Informationen zu Mono finden Sie in der [Mono-Dokumentation](http://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="00477-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="00477-215">.NET</span><span class="sxs-lookup"><span data-stu-id="00477-215">.NET</span></span>

<span data-ttu-id="00477-216">Der Oberbegriff für [.NET Standard](#net-standard) und alle [.NET-Implementierungen](#implementation-of-net) und Workloads.</span><span class="sxs-lookup"><span data-stu-id="00477-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="00477-217">Immer groß geschrieben, niemals „.Net“.</span><span class="sxs-lookup"><span data-stu-id="00477-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="00477-218">Siehe [Leitfaden für .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="00477-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="00477-219">.NET Core</span><span class="sxs-lookup"><span data-stu-id="00477-219">.NET Core</span></span> 

<span data-ttu-id="00477-220">Eine plattformübergreifende, leistungsstarke Open Source-Implementierung von .NET.</span><span class="sxs-lookup"><span data-stu-id="00477-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="00477-221">Enthält die Common Language Runtime (CoreCLR), die Core AOT Runtime (CoreRT, in der Entwicklung), die Core-Basisklassenbibliothek und das Core SDK.</span><span class="sxs-lookup"><span data-stu-id="00477-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="00477-222">Siehe [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="00477-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="00477-223">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="00477-223">.NET Core CLI</span></span>

<span data-ttu-id="00477-224">Eine plattformübergreifende Toolkette zum Entwickeln von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="00477-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="00477-225">Siehe [Tools für die .NET Core-Befehlszeilenschnittstelle (CLI)](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="00477-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="00477-226">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="00477-226">.NET Core SDK</span></span>

<span data-ttu-id="00477-227">Eine Sammlung von Bibliotheken und Tools, mit der Entwickler .NET Core-Anwendungen und -Bibliotheken erstellen können.</span><span class="sxs-lookup"><span data-stu-id="00477-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="00477-228">Enthält die [.NET Core-CLI](#net-core-cli) zum Erstellen von Apps, die .NET Core-Bibliotheken und -Runtime zum Erstellen und Ausführen von Apps und die ausführbare dotnet-Datei (*dotnet.exe*), durch die CLI-Befehle und Anwendungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00477-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="00477-229">Siehe [.NET Core SDK – Übersicht](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="00477-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="00477-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="00477-230">.NET Framework</span></span>

<span data-ttu-id="00477-231">Eine Implementierung von .NET, die nur unter Windows ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="00477-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="00477-232">Enthält die Common Language Runtime (CLR), die Basisklassenbibliothek und Bibliotheken für Anwendungsframeworks wie ASP.NET, Windows Forms und WPF.</span><span class="sxs-lookup"><span data-stu-id="00477-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="00477-233">Siehe [Leitfaden für .NET Framework](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="00477-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="00477-234">.NET systemeigen</span><span class="sxs-lookup"><span data-stu-id="00477-234">.NET Native</span></span>

<span data-ttu-id="00477-235">Eine Compiler-Toolkette, die nativen Code vorzeitig (Ahead-of-Time, AOT) statt rechtzeitig (Just-in-Time, JIT) erzeugt.</span><span class="sxs-lookup"><span data-stu-id="00477-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="00477-236">Die Kompilierung erfolgt auf dem Computer des Entwicklers und funktioniert ähnlich wie ein C++-Compiler und -Linker.</span><span class="sxs-lookup"><span data-stu-id="00477-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="00477-237">Nicht verwendeter Code wird entfernt und es wird mehr Zeit in die Optimierung des Codes investiert.</span><span class="sxs-lookup"><span data-stu-id="00477-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="00477-238">Es wird Code aus den Bibliotheken extrahiert und in die ausführbare Datei eingefügt.</span><span class="sxs-lookup"><span data-stu-id="00477-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="00477-239">Das Ergebnis ist ein einzelnes Modul, das die gesamte App darstellt.</span><span class="sxs-lookup"><span data-stu-id="00477-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="00477-240">UWP war das erste Anwendungsframework, das von .NET Native unterstützt wurde.</span><span class="sxs-lookup"><span data-stu-id="00477-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="00477-241">Nun unterstützen wir das Erstellen nativer Konsolen-Apps unter Windows, macOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="00477-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="00477-242">Siehe [Intro to .NET Native and CoreRT (Einführung in .NET Native und CoreRT)](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="00477-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="00477-243">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="00477-243">.NET Standard</span></span>

<span data-ttu-id="00477-244">Eine formale Spezifikation der .NET-APIs, die in jeder .NET-Implementierung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00477-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="00477-245">Die Spezifikation von .NET Standard wird in der Dokumentation manchmal als „Bibliothek“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="00477-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="00477-246">Da eine Bibliothek API-Implementierungen enthält und nicht nur Spezifikationen (Schnittstellen), ist es irreführend, .NET Standard als „Bibliothek“ zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="00477-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="00477-247">Diese Verwendung soll aus der Dokumentation beseitigt werden. Ausgenommen davon ist der Verweis auf den Namen des .NET Standard-Metapakets (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="00477-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="00477-248">Siehe [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="00477-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="00477-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="00477-249">NGEN</span></span>

<span data-ttu-id="00477-250">Native Imagegenerierung</span><span class="sxs-lookup"><span data-stu-id="00477-250">Native (image) generation.</span></span>

<span data-ttu-id="00477-251">Sie können sich diese Technologie als einen permanenten JIT-Compiler vorstellen.</span><span class="sxs-lookup"><span data-stu-id="00477-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="00477-252">Normalerweise wird der Code auf dem Computer kompiliert, auf dem er ausgeführt wird. Die Kompilierung findet jedoch normalerweise während der Installation statt.</span><span class="sxs-lookup"><span data-stu-id="00477-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="00477-253">package</span><span class="sxs-lookup"><span data-stu-id="00477-253">package</span></span>

<span data-ttu-id="00477-254">Ein NuGet-Paket &mdash; oder nur ein Paket &mdash; ist eine *ZIP*-Datei mit mindestens einer Assembly, die denselben Namen trägt und zusätzlichen Metadaten, z.B. der Autorenname.</span><span class="sxs-lookup"><span data-stu-id="00477-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="00477-255">Die *ZIP*-Datei besitzt eine *NUPKG*-Erweiterung und eventuell Ressourcen, z.B. *DLL*- und *XML*-Dateien, für die Verwendung mit mehreren Zielframeworks und Versionen.</span><span class="sxs-lookup"><span data-stu-id="00477-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="00477-256">Bei der Installation in einer App oder Bibliothek werden die entsprechenden Ressourcen basierend auf dem Zielframework ausgeführt, das von der App oder Bibliothek angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="00477-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="00477-257">Die Ressourcen, die die Schnittstelle definieren, befinden sich im Ordner *ref*, und die Ressourcen, die die Implementierung definieren, befinden sich im Ordner *lib*.</span><span class="sxs-lookup"><span data-stu-id="00477-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="00477-258">platform</span><span class="sxs-lookup"><span data-stu-id="00477-258">platform</span></span>

<span data-ttu-id="00477-259">Ein Betriebssystem (z.B. Windows, macOS, Linux, iOS und Android) und die Hardware, auf dem dieses ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00477-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="00477-260">Hier sind Beispiele für die Verwendung in Sätzen:</span><span class="sxs-lookup"><span data-stu-id="00477-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="00477-261">„.NET Core ist eine plattformübergreifende Implementierung von .NET.“</span><span class="sxs-lookup"><span data-stu-id="00477-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="00477-262">„PCL-Profile stehen für Microsoft-Plattformen, während .NET Standard plattformunabhängig ist.“</span><span class="sxs-lookup"><span data-stu-id="00477-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="00477-263">Die .NET-Dokumentation verwendet häufig „.NET-Plattform“, um sich entweder auf eine Implementierung von .NET oder den .NET-Stapel, der alle Implementierungen enthält, zu beziehen.</span><span class="sxs-lookup"><span data-stu-id="00477-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="00477-264">Beide dieser Verwendungen werden häufig mit der primären Bedeutung (Betriebssystem/Hardware) verwechselt, sodass wir diese Verwendungen aus der Dokumentation beseitigen werden.</span><span class="sxs-lookup"><span data-stu-id="00477-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="00477-265">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="00477-265">runtime</span></span>

<span data-ttu-id="00477-266">Die Ausführungsumgebung eines verwalteten Programms.</span><span class="sxs-lookup"><span data-stu-id="00477-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="00477-267">Das Betriebssystem ist Teil der Laufzeitumgebung, gehört jedoch nicht zur .NET-Runtime.</span><span class="sxs-lookup"><span data-stu-id="00477-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="00477-268">Dies sind einige Beispiele für .NET-Runtimes:</span><span class="sxs-lookup"><span data-stu-id="00477-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="00477-269">Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="00477-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="00477-270">Core Common Language Runtime (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="00477-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="00477-271">.NET Native (für UWP)</span><span class="sxs-lookup"><span data-stu-id="00477-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="00477-272">Mono Runtime</span><span class="sxs-lookup"><span data-stu-id="00477-272">Mono runtime</span></span>

<span data-ttu-id="00477-273">Die .NET-Dokumentation bezeichnet mit „Runtime“ manchmal eine Implementierung von .NET.</span><span class="sxs-lookup"><span data-stu-id="00477-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="00477-274">Beispielsweise sollte „Runtime“ in den folgenden Sätzen durch „Implementierung“ ersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="00477-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="00477-275">„Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen von .NET Standard.“</span><span class="sxs-lookup"><span data-stu-id="00477-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="00477-276">„Bibliotheken, die auf mehreren Runtimes ausgeführt werden sollen, sollten dieses Framework als Ziel haben.“</span><span class="sxs-lookup"><span data-stu-id="00477-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="00477-277">(bezogen auf .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="00477-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="00477-278">„Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen von .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="00477-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="00477-279">…</span><span class="sxs-lookup"><span data-stu-id="00477-279">…</span></span> <span data-ttu-id="00477-280">Jede Version der .NET-Runtime kündigt die höchste Version von .NET Standard an, die sie unterstützt ...“</span><span class="sxs-lookup"><span data-stu-id="00477-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="00477-281">Diese inkonsistente Verwendung soll beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="00477-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="00477-282">Stapel</span><span class="sxs-lookup"><span data-stu-id="00477-282">stack</span></span>

<span data-ttu-id="00477-283">Eine Reihe von Programmiertechnologien, die zusammen verwendet werden, um Anwendungen zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="00477-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="00477-284">„Der .NET-Stapel“ bezieht sich auf .NET Standard und alle .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="00477-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="00477-285">Der Ausdruck „ein .NET-Stapel“ bezieht sich auf eine Implementierung von .NET.</span><span class="sxs-lookup"><span data-stu-id="00477-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="00477-286">Zielframework</span><span class="sxs-lookup"><span data-stu-id="00477-286">target framework</span></span>

<span data-ttu-id="00477-287">Die Sammlung von APIs, auf der eine .NET-App oder -Bibliothek basiert.</span><span class="sxs-lookup"><span data-stu-id="00477-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="00477-288">Eine App oder Bibliothek kann eine Version von .NET Standard (beispielsweise .NET Standard 2.0) anzielen. Dabei handelt es sich um eine Spezifikation für eine standardisierte Reihe von APIs für alle .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="00477-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="00477-289">Eine App oder Bibliothek kann auch eine Version einer bestimmten .NET-Implementierung anzielen. In diesem Fall erhält diese Zugriff auf die implementierungsspezifischen APIs.</span><span class="sxs-lookup"><span data-stu-id="00477-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="00477-290">Beispielsweise erhält eine App, die Xamarin iOS anzieht, Zugriff auf die von Xamarin bereitgestellten iOS-API-Wrapper.</span><span class="sxs-lookup"><span data-stu-id="00477-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="00477-291">Für einige Zielplattformen (z.B. .NET Framework) werden die verfügbaren APIs von den Assemblys definiert, die eine .NET-Implementierung auf einem System installiert, zu denen Anwendungsframework-APIs zählen können (z.B. ASP.NET, WinForms).</span><span class="sxs-lookup"><span data-stu-id="00477-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="00477-292">Für paketbasierte Zielframeworks (z.B. .NET Standard und .NET Core) werden die Framework-APIs von den Paketen definiert, die in der App oder der Bibliothek installiert sind.</span><span class="sxs-lookup"><span data-stu-id="00477-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="00477-293">In diesem Fall gibt das Zielframework implizit ein Metapaket an, das auf alle Pakete verweist, aus denen das Framework besteht.</span><span class="sxs-lookup"><span data-stu-id="00477-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="00477-294">Siehe [Zielframeworks](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="00477-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="00477-295">TFM</span><span class="sxs-lookup"><span data-stu-id="00477-295">TFM</span></span>

<span data-ttu-id="00477-296">Zielframeworkmoniker</span><span class="sxs-lookup"><span data-stu-id="00477-296">Target framework moniker.</span></span>

<span data-ttu-id="00477-297">Ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="00477-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="00477-298">Auf Zielframeworks wird üblicherweise durch einen kurzen Namen verwiesen, z.B. `net462`.</span><span class="sxs-lookup"><span data-stu-id="00477-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="00477-299">Es gibt auch lange TFMs (z.B. .NETFramework, Version = 4.6.2). Diese werden aber im Allgemeinen nicht verwendet, um ein Zielframework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="00477-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="00477-300">Siehe [Zielframeworks](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="00477-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="00477-301">UWP</span><span class="sxs-lookup"><span data-stu-id="00477-301">UWP</span></span>

<span data-ttu-id="00477-302">Universelle Windows-Plattform</span><span class="sxs-lookup"><span data-stu-id="00477-302">Universal Windows Platform.</span></span>

<span data-ttu-id="00477-303">Eine Implementierung von .NET, mit der moderne Touchscreen-Windows-Anwendungen und Software für das Internet der Dinge (Internet of Things, IoT) erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="00477-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="00477-304">Sie wurde als einheitliche Plattform entwickelt, um das Programmieren für verschiedene Gerätetypen, von PCs, Tablets, Phablets über Smartphones bis hin zur Xbox, zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="00477-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="00477-305">Die UWP bietet viele Dienste, z.B. einen zentralen App Store, eine Ausführungsumgebung (AppContainer) und mehrere Windows-APIs, die anstelle von Win32 (WinRT) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00477-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="00477-306">Apps können auf dieser Plattform in C++, C#, VB.NET und JavaScript geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="00477-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="00477-307">Die .NET-APIs für C# und VB.NET werden von .NET Core bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="00477-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="00477-308">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00477-308">See also</span></span>

[<span data-ttu-id="00477-309">.NET Guide (Leitfaden für .NET)</span><span class="sxs-lookup"><span data-stu-id="00477-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="00477-310">Leitfaden für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="00477-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="00477-311">.NET Core</span><span class="sxs-lookup"><span data-stu-id="00477-311">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="00477-312">ASP.NET Overview (Übersicht über ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="00477-312">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="00477-313">ASP.NET Core Overview (Übersicht über ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="00477-313">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

