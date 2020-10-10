---
title: Übersicht über die ReadyToRun-Bereitstellung
description: Erfahren Sie, was ReadyToRun-Bereitstellungen sind und warum Sie diese als Teil Ihrer App-Veröffentlichung mit .NET 5 und .NET Core 3.0 und höher in Erwägung ziehen sollten.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: b4052a0c0f4ed9f6cfd273abe5ef45d018bd0ae0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654946"
---
# <a name="readytorun-compilation"></a><span data-ttu-id="6e57e-103">ReadyToRun-Kompilierung</span><span class="sxs-lookup"><span data-stu-id="6e57e-103">ReadyToRun Compilation</span></span>

<span data-ttu-id="6e57e-104">Die Start- und Wartezeiten für .NET-Anwendungen können verbessert werden, indem Sie Ihre Anwendungsassemblys im R2R-Format (ReadyToRun) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6e57e-104">.NET application startup time and latency can be improved by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="6e57e-105">R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time).</span><span class="sxs-lookup"><span data-stu-id="6e57e-105">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="6e57e-106">R2R-Binärdateien verbessern die Startleistung, indem sie den Arbeitsaufwand des JIT-Compilers (Just-in-time) reduzieren, der anfällt, wenn Ihre Anwendung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6e57e-106">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="6e57e-107">Die Binärdateien enthalten ähnlichen nativen Code im Vergleich zu dem, was der JIT-Compiler produzieren würde.</span><span class="sxs-lookup"><span data-stu-id="6e57e-107">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="6e57e-108">R2R-Binärdateien sind jedoch größer, da sie sowohl IL-Code (Intermediate Language, Zwischensprache), der für einige Szenarios noch benötigt wird, als auch die native Version des gleichen Codes enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e57e-108">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="6e57e-109">R2R ist nur bei Veröffentlichung einer App verfügbar, die auf bestimmte Laufzeitumgebungen (RID) wie Linux x64 oder Windows x64 ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6e57e-109">R2R is only available when you publish an app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="6e57e-110">Damit Ihr Projekt als ReadyToRun kompiliert werden kann, muss die PublishReadyToRun-Eigenschaft bei der Anwendungsveröffentlichung auf TRUE festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="6e57e-110">To compile your project as ReadyToRun, the application must be published with the PublishReadyToRun property set to true.</span></span>

<span data-ttu-id="6e57e-111">Es gibt zwei Möglichkeiten, Ihre App als ReadyToRun zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="6e57e-111">There are two ways to publish your app as ReadyToRun:</span></span>

01. <span data-ttu-id="6e57e-112">Geben Sie das Flag „PublishReadyToRun“ direkt im Befehl „dotnet publish“ an.</span><span class="sxs-lookup"><span data-stu-id="6e57e-112">Specify the PublishReadyToRun flag directly to the dotnet publish command.</span></span> <span data-ttu-id="6e57e-113">Weitere Informationen finden Sie unter [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="6e57e-113">See [dotnet publish](../tools/dotnet-publish.md) for details.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. <span data-ttu-id="6e57e-114">Geben Sie die Eigenschaft im Projekt an.</span><span class="sxs-lookup"><span data-stu-id="6e57e-114">Specify the property in the project</span></span>

    - <span data-ttu-id="6e57e-115">Fügen Sie Ihrem Projekt die Einstellung `<PublishReadyToRun>` hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e57e-115">Add the `<PublishReadyToRun>` setting to your project.</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - <span data-ttu-id="6e57e-116">Veröffentlichen Sie die Anwendung ohne spezielle Parameter.</span><span class="sxs-lookup"><span data-stu-id="6e57e-116">Publish the application without any special parameters.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a><span data-ttu-id="6e57e-117">Auswirkungen der Verwendung des ReadyToRun-Features</span><span class="sxs-lookup"><span data-stu-id="6e57e-117">Impact of using the ReadyToRun feature</span></span>

<span data-ttu-id="6e57e-118">Die Ahead-of-time-Kompilierung besitzt komplexe Auswirkungen auf die Anwendungsleistung, die sich möglicherweise nur schwer vorhersagen lassen.</span><span class="sxs-lookup"><span data-stu-id="6e57e-118">Ahead-of-time compilation has complex performance impact on application performance, which may be difficult to predict.</span></span> <span data-ttu-id="6e57e-119">Im allgemeinen wächst die Größe einer Assembly auf das Zwei- bis Dreifache an.</span><span class="sxs-lookup"><span data-stu-id="6e57e-119">In general, the size of an assembly will grow to between two to three times larger.</span></span> <span data-ttu-id="6e57e-120">Durch diese Zunahme der physischen Dateigröße kann sich die Leistung beim Laden der Assembly von einem Datenträger verringern und der Arbeitssatz des Prozesses erhöhen.</span><span class="sxs-lookup"><span data-stu-id="6e57e-120">This increase in the physical size of the file may reduce the performance of loading the assembly from disk, and increase working set of the process.</span></span> <span data-ttu-id="6e57e-121">Auf der anderen Seite wird die Anzahl von Methoden, die zur Laufzeit kompiliert werden, in der Regel erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="6e57e-121">However, in return the number of methods compiled at runtime is typically reduced substantially.</span></span> <span data-ttu-id="6e57e-122">Unterm Strich können die meisten Anwendungen mit umfangreichem Code durch die Aktivierung von ReadyToRun von großen Leistungsvorteilen profitieren.</span><span class="sxs-lookup"><span data-stu-id="6e57e-122">The result is that most applications that large amounts of code receive large performance benefits from enabling ReadyToRun.</span></span> <span data-ttu-id="6e57e-123">Bei Anwendungen, die nur eine geringe Codemenge umfassen, können durch die Aktivierung von ReadyToRun wahrscheinlich keine wesentliche Verbesserung erzielen, weil die .NET-Runtimebibliotheken bereits mit ReadyToRun vorkompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="6e57e-123">Applications, which have small amounts of code will likely not experience a significant improvement from enabling ReadyToRun, as the .NET runtime libraries have already been precompiled with ReadyToRun.</span></span>

<span data-ttu-id="6e57e-124">Die hier beschriebene Startverbesserung gilt nicht nur für den Anwendungsstart, sondern auch für die erste Verwendung von Code in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6e57e-124">The startup improvement discussed here applies not only to application startup, but also to the first use of any code in the application.</span></span> <span data-ttu-id="6e57e-125">So kann beispielsweise die Antwortlatenz bei der ersten Verwendung der Web-API in einer ASP.NET-Anwendung mithilfe von ReadyToRun reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="6e57e-125">For instance, ReadyToRun can be used to reduce the response latency of the first use  of Web API in an ASP.NET application.</span></span>

### <a name="interaction-with-tiered-compilation"></a><span data-ttu-id="6e57e-126">Interaktion mit mehrstufiger Kompilierung</span><span class="sxs-lookup"><span data-stu-id="6e57e-126">Interaction with tiered compilation</span></span>

<span data-ttu-id="6e57e-127">Der durch die Ahead-of-time-Kompilierung generierte Code ist nicht so hoch optimiert wie Code, der durch die JIT-Kompilierung erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="6e57e-127">Ahead-of-time generated is not as highly optimized as code produced by the JIT.</span></span> <span data-ttu-id="6e57e-128">Um dieses Problem zu beheben, werden bei der mehrstufigen Kompilierung häufig verwendete ReadyToRun-Methoden durch JIT-generierte Methoden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6e57e-128">To address this issue, tiered compilation will replace commonly used ReadyToRun methods with JIT-generated methods.</span></span>

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a><span data-ttu-id="6e57e-129">Wie wird der Satz vorkompilierter Assemblys ausgewählt?</span><span class="sxs-lookup"><span data-stu-id="6e57e-129">How is the set of precompiled assemblies chosen?</span></span>

<span data-ttu-id="6e57e-130">Das SDK führt eine Vorkompilierung der Assemblys aus, die mit der Anwendung verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="6e57e-130">The SDK will precompile the assemblies that are distributed with the application.</span></span> <span data-ttu-id="6e57e-131">Bei eigenständigen Anwendungen schließt dieser Satz von Assemblys das Framework mit ein.</span><span class="sxs-lookup"><span data-stu-id="6e57e-131">For self-contained applications, this set of assemblies will include the framework.</span></span> <span data-ttu-id="6e57e-132">C++-/CLI-Binärdateien sind für die ReadyToRun-Kompilierung nicht geeignet.</span><span class="sxs-lookup"><span data-stu-id="6e57e-132">C++/CLI binaries are not eligible for ReadyToRun compilation.</span></span>

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a><span data-ttu-id="6e57e-133">Wie wird der Satz von Methoden für die Vorkompilierung ausgewählt?</span><span class="sxs-lookup"><span data-stu-id="6e57e-133">How is the set of methods to precompile chosen?</span></span>

<span data-ttu-id="6e57e-134">Der Compiler versucht, so viele Methoden wie möglich vorab zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6e57e-134">The compiler will attempt to pre-compile as many methods as it can.</span></span> <span data-ttu-id="6e57e-135">Aus verschiedenen Gründen ist jedoch nicht zu erwarten, dass die Verwendung des ReadyToRun-Features eine JIT-Ausführung verhindert.</span><span class="sxs-lookup"><span data-stu-id="6e57e-135">However various reasons it is not expected that using the ReadyToRun feature will result in preventing the JIT from executing.</span></span>

<span data-ttu-id="6e57e-136">Hierzu gehören:</span><span class="sxs-lookup"><span data-stu-id="6e57e-136">Such reasons may include, but are not limited to:</span></span>

- <span data-ttu-id="6e57e-137">Verwendung generischer Typen, die in separaten Assemblys definiert sind</span><span class="sxs-lookup"><span data-stu-id="6e57e-137">Use of generic types defined in separate assemblies</span></span>
- <span data-ttu-id="6e57e-138">Interop mit nativem Code</span><span class="sxs-lookup"><span data-stu-id="6e57e-138">Interop with native code</span></span>
- <span data-ttu-id="6e57e-139">Verwendung systeminterner Hardwarefunktionen, deren Verwendung auf einem Zielcomputer vom Compiler nicht als sicher eingestuft werden kann</span><span class="sxs-lookup"><span data-stu-id="6e57e-139">Use of hardware intrinsics that the compiler cannot prove are safe to use on a target machine</span></span>
- <span data-ttu-id="6e57e-140">Bestimmte ungewöhnliche IL-Muster</span><span class="sxs-lookup"><span data-stu-id="6e57e-140">Certain unusual IL patterns</span></span>
- <span data-ttu-id="6e57e-141">Dynamische Methodenerstellung über Reflexion oder LINQ</span><span class="sxs-lookup"><span data-stu-id="6e57e-141">Dynamic method creation via reflection, or LINQ</span></span>

## <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="6e57e-142">Plattformübergreifende bzw. architekturbezogene Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6e57e-142">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="6e57e-143">Für einige SDK-Plattformen kann der ReadyToRun-Compiler eine Crosskompilierung für andere Zielplattformen durchführen.</span><span class="sxs-lookup"><span data-stu-id="6e57e-143">For some SDK platforms, the ReadyToRun compiler is capable of cross-compiling for other target platforms.</span></span> <span data-ttu-id="6e57e-144">Unterstützte Kompilierungsziele werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e57e-144">Supported compilation targets are described in the table below.</span></span>

| <span data-ttu-id="6e57e-145">SDK-Plattform</span><span class="sxs-lookup"><span data-stu-id="6e57e-145">SDK platform</span></span> | <span data-ttu-id="6e57e-146">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="6e57e-146">Supported target platforms</span></span> |
| ------------ | --------------------------- |
| <span data-ttu-id="6e57e-147">Windows X64</span><span class="sxs-lookup"><span data-stu-id="6e57e-147">Windows X64</span></span>  | <span data-ttu-id="6e57e-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span><span class="sxs-lookup"><span data-stu-id="6e57e-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span></span> |
| <span data-ttu-id="6e57e-149">Windows X86</span><span class="sxs-lookup"><span data-stu-id="6e57e-149">Windows X86</span></span>  | <span data-ttu-id="6e57e-150">Windows X86, Windows ARM32</span><span class="sxs-lookup"><span data-stu-id="6e57e-150">Windows X86, Windows ARM32</span></span> |
| <span data-ttu-id="6e57e-151">Linux X64</span><span class="sxs-lookup"><span data-stu-id="6e57e-151">Linux X64</span></span>    | <span data-ttu-id="6e57e-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="6e57e-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span></span> |
| <span data-ttu-id="6e57e-153">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="6e57e-153">Linux ARM32</span></span>  | <span data-ttu-id="6e57e-154">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="6e57e-154">Linux ARM32</span></span> |
| <span data-ttu-id="6e57e-155">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="6e57e-155">Linux ARM64</span></span>  | <span data-ttu-id="6e57e-156">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="6e57e-156">Linux ARM64</span></span> |
| <span data-ttu-id="6e57e-157">macOS X64</span><span class="sxs-lookup"><span data-stu-id="6e57e-157">macOS X64</span></span>    | <span data-ttu-id="6e57e-158">macOS X64</span><span class="sxs-lookup"><span data-stu-id="6e57e-158">macOS X64</span></span> |
