---
title: Erstellen von .NET Core aus einer Quelle
description: Erfahren Sie, wie Sie .NET Core und .NET Core-CLI aus dem Quellcode erstellen.
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.openlocfilehash: 2623c5d21121b71960d174301c35bdd0d7f8558a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198867"
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="d799a-103">Erstellen von .NET Core aus einer Quelle</span><span class="sxs-lookup"><span data-stu-id="d799a-103">Build .NET Core from source</span></span>

<span data-ttu-id="d799a-104">Die Möglichkeit, .NET Core aus dem Quellcode zu erstellen, ist auf verschiedene Weise wichtig: Es erleichtert das Portieren von .NET Core auf neue Plattformen, es ermöglicht Beiträge und Korrekturen des Produkts, und es ermöglicht das Erstellen von benutzerdefinierten Versionen von .NET.</span><span class="sxs-lookup"><span data-stu-id="d799a-104">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="d799a-105">Dieser Artikel enthält eine Anleitung für Entwickler, die ihre eigenen Versionen von .NET Core erstellen und verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="d799a-105">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="d799a-106">Erstellen der CLR aus der Quelle</span><span class="sxs-lookup"><span data-stu-id="d799a-106">Build the CLR from source</span></span>

<span data-ttu-id="d799a-107">Den Quellcode für .NET CoreCLR finden Sie im Repository [dotnet/coreclr](https://github.com/dotnet/coreclr/) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d799a-107">The source code for the .NET CoreCLR can be found in the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository on GitHub.</span></span>

<span data-ttu-id="d799a-108">Der Build hängt derzeit von folgenden Voraussetzungen ab:</span><span class="sxs-lookup"><span data-stu-id="d799a-108">The build currently depends on the following prerequisites:</span></span>

* [<span data-ttu-id="d799a-109">Git</span><span class="sxs-lookup"><span data-stu-id="d799a-109">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="d799a-110">CMake</span><span class="sxs-lookup"><span data-stu-id="d799a-110">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="d799a-111">Python</span><span class="sxs-lookup"><span data-stu-id="d799a-111">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="d799a-112">ein C++-Compiler.</span><span class="sxs-lookup"><span data-stu-id="d799a-112">a C++ compiler.</span></span>

<span data-ttu-id="d799a-113">Nach der Installation dieser Komponenten können Sie die CLR erstellen, indem Sie das Buildskript (`build.cmd` unter Windows oder `build.sh` unter Linux und macOS) an der Basis des Repositorys [dotnet/coreclr](https://github.com/dotnet/coreclr/) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d799a-113">After you've installed these prerequisites, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository.</span></span>

<span data-ttu-id="d799a-114">Das Installieren der Komponenten unterscheidet sich je nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="d799a-114">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="d799a-115">Weitere Informationen finden Sie in den Buildanweisungen Ihres Betriebssystems:</span><span class="sxs-lookup"><span data-stu-id="d799a-115">See the build instructions for your specific OS:</span></span>

* [<span data-ttu-id="d799a-116">Windows</span><span class="sxs-lookup"><span data-stu-id="d799a-116">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
* [<span data-ttu-id="d799a-117">Linux</span><span class="sxs-lookup"><span data-stu-id="d799a-117">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
* [<span data-ttu-id="d799a-118">macOS</span><span class="sxs-lookup"><span data-stu-id="d799a-118">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
* [<span data-ttu-id="d799a-119">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="d799a-119">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
* [<span data-ttu-id="d799a-120">NetBSD</span><span class="sxs-lookup"><span data-stu-id="d799a-120">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="d799a-121">Es gibt keine betriebssystemübergreifenden Erstellungen (nur für ARM, das in X64 erstellt wurde).</span><span class="sxs-lookup"><span data-stu-id="d799a-121">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="d799a-122">Sie müssen sich auf der speziellen Plattform befinden, um diese Plattform zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d799a-122">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="d799a-123">Der Build verfügt über zwei Haupt-`buildTypes`:</span><span class="sxs-lookup"><span data-stu-id="d799a-123">The build has two main `buildTypes`:</span></span>

* <span data-ttu-id="d799a-124">Debuggen (Standard): Kompiliert die Runtime mit minimalen Optimierungen und zusätzlichen Überprüfungen der Runtime (Assert-Vorgänge).</span><span class="sxs-lookup"><span data-stu-id="d799a-124">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="d799a-125">Diese minimierte Optimierungsstufe und die zusätzlichen Überprüfungen verlangsamen die Runtimeausführung, sind aber wichtig für das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="d799a-125">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="d799a-126">Dies ist die empfohlene Einstellung für Entwicklungs- und Testumgebungen.</span><span class="sxs-lookup"><span data-stu-id="d799a-126">This is the recommended setting for development and testing environments.</span></span>
* <span data-ttu-id="d799a-127">Release: Kompiliert die Runtime mit vollständigen Optimierungen, aber ohne die zusätzlichen Überprüfungen der Runtime.</span><span class="sxs-lookup"><span data-stu-id="d799a-127">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="d799a-128">Dies führt zu einer wesentlich schnelleren Leistung der Runtime, die Erstellung des Builds kann jedoch länger dauern, und das Debuggen kann schwieriger sein.</span><span class="sxs-lookup"><span data-stu-id="d799a-128">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="d799a-129">Übergeben Sie `release` an das Buildskript, um diesen Buildtyp auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d799a-129">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="d799a-130">Darüber hinaus erstellt der Build standardmäßig nicht nur ausführbare Dateien für die Runtime, sondern auch alle Tests.</span><span class="sxs-lookup"><span data-stu-id="d799a-130">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="d799a-131">Es gibt einige Tests, die viel Zeit in Anspruch nehmen, was jedoch nicht nötig ist, wenn Sie nur mit Änderungen experimentieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d799a-131">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="d799a-132">Sie können die Testbuilds überspringen, indem Sie das Argument `skiptests` zum Buildskript hinzufügen, wie im folgenden Beispiel (ersetzen Sie `.\build` durch `./build.sh` auf Unix-Computern):</span><span class="sxs-lookup"><span data-stu-id="d799a-132">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests
```

<span data-ttu-id="d799a-133">Im vorherigen Beispiel wurde gezeigt, wie die `Debug`-Konfiguration erstellt wird, bei der Überprüfungen zur Entwicklungszeit (Assert-Vorgänge) und Optimierungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d799a-133">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="d799a-134">Führen Sie folgende Schritte aus, um die Releasekonfiguration (volle Geschwindigkeit) zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d799a-134">To build the release (full speed) flavor, do the following:</span></span>

```bat
    .\build release skiptests
```

<span data-ttu-id="d799a-135">Sie können mit „build“ weitere Buildoptionen finden, indem Sie den Qualifizierer „-?“</span><span class="sxs-lookup"><span data-stu-id="d799a-135">You can find more build options with build by using the -?</span></span> <span data-ttu-id="d799a-136">oder „-help“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="d799a-136">or -help qualifier.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="d799a-137">Verwenden Ihres Builds</span><span class="sxs-lookup"><span data-stu-id="d799a-137">Using Your Build</span></span>

<span data-ttu-id="d799a-138">Der Build platziert alle seine generierten Dateien in das `bin`-Verzeichnis an der Basis des Repository.</span><span class="sxs-lookup"><span data-stu-id="d799a-138">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="d799a-139">Es gibt ein *bin\Log*-Verzeichnis, das während des Erstellungsvorgangs generierte Protokolldateien enthält (besonders hilfreich, wenn der Buildvorgang scheitert).</span><span class="sxs-lookup"><span data-stu-id="d799a-139">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="d799a-140">Die tatsächliche Ausgabe befindet sich in einem Verzeichnis *bin\Product\[Plattform].[CPU-Architektur].[Buildtyp]*, z.B. *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="d799a-140">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="d799a-141">Während die „rohe“ Ausgabe des Builds in einigen Fällen nützlich ist, sind  normalerweise nur die NuGet-Paketen für Sie von Interesse, die sich im Unterverzeichnis `.nuget\pkg` des vorherigen Ausgabeverzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="d799a-141">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="d799a-142">Es gibt zwei grundlegende Verfahren für die Verwendung der neuen Runtime:</span><span class="sxs-lookup"><span data-stu-id="d799a-142">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="d799a-143">**Verwenden Sie zum Verfassen einer Anwendung „dotnet.exe“ und NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d799a-143">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="d799a-144">Unter [Using Your Build (Verwenden Ihres Builds)](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) finden Sie Anweisungen zum Erstellen eines Programms, das Ihre neue Runtime verwendet, indem es die NuGet-Pakete, die Sie zuvor erstellt haben, und die „dotnet“-CLI verwendet.</span><span class="sxs-lookup"><span data-stu-id="d799a-144">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="d799a-145">Diese Technik ist die erwartete Methode, mit der Entwickler ohne Runtime wahrscheinlich Ihre neue Runtime nutzen.</span><span class="sxs-lookup"><span data-stu-id="d799a-145">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>

 2. <span data-ttu-id="d799a-146">**Verwenden Sie „corerun.exe“ zum Ausführen einer Anwendung, die unverpackte DLLs verwendet**.</span><span class="sxs-lookup"><span data-stu-id="d799a-146">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="d799a-147">Dieses Repository definiert außerdem einen einfachen Host mit dem Namen „corerun.exe“, der NICHT von NuGet abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="d799a-147">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="d799a-148">Sie müssen den Host darüber informieren, wo er die benötigten DLLs erhält, die Sie tatsächlich verwenden, und Sie müssen sie manuell sammeln.</span><span class="sxs-lookup"><span data-stu-id="d799a-148">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="d799a-149">Diese Technik wird von allen Tests im Repository [dotnet/coreclr](https://github.com/dotnet/coreclr) verwendet und eignet sich zur schnellen lokalen „Bearbeiten-Kompilieren-Debuggen“-Schleife, z.B. für vorläufige Komponententests.</span><span class="sxs-lookup"><span data-stu-id="d799a-149">This technique is used by all the tests in the [dotnet/coreclr](https://github.com/dotnet/coreclr) repo, and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="d799a-150">Weitere Informationen zur Verwendung dieser Technik finden Sie unter [Executing .NET Core Apps with CoreRun.exe (Ausführen von .NET Core-Apps mit „CoreRun.exe“)](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md).</span><span class="sxs-lookup"><span data-stu-id="d799a-150">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="d799a-151">Erstellen der CLI aus der Quelle</span><span class="sxs-lookup"><span data-stu-id="d799a-151">Build the CLI from source</span></span>

<span data-ttu-id="d799a-152">Den Quellcode für die .NET Core-CLI finden Sie im Repository [dotnet/cli](https://github.com/dotnet/cli/) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d799a-152">The source code for the .NET Core CLI can be found in the [dotnet/cli](https://github.com/dotnet/cli/) repository on GitHub.</span></span>

<span data-ttu-id="d799a-153">Um die .NET Core-CLI zu erstellen, müssen Sie Folgendes auf dem Computer installiert haben.</span><span class="sxs-lookup"><span data-stu-id="d799a-153">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="d799a-154">Windows & Linux:</span><span class="sxs-lookup"><span data-stu-id="d799a-154">Windows & Linux:</span></span>
  * <span data-ttu-id="d799a-155">Git auf dem Pfad</span><span class="sxs-lookup"><span data-stu-id="d799a-155">git on the PATH</span></span>
* <span data-ttu-id="d799a-156">macOS:</span><span class="sxs-lookup"><span data-stu-id="d799a-156">macOS:</span></span>
  * <span data-ttu-id="d799a-157">Git auf dem Pfad</span><span class="sxs-lookup"><span data-stu-id="d799a-157">git on the PATH</span></span>
  * <span data-ttu-id="d799a-158">Xcode</span><span class="sxs-lookup"><span data-stu-id="d799a-158">Xcode</span></span>
  * <span data-ttu-id="d799a-159">OpenSSL</span><span class="sxs-lookup"><span data-stu-id="d799a-159">OpenSSL</span></span>

<span data-ttu-id="d799a-160">Führen Sie zum Erstellen `build.cmd` unter Windows oder `build.sh` unter Linux und macOS aus dem Stamm aus.</span><span class="sxs-lookup"><span data-stu-id="d799a-160">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="d799a-161">Wenn Sie keine Tests ausführen möchten, führen Sie `build.cmd /t:Compile` oder `./build.sh /t:Compile` aus.</span><span class="sxs-lookup"><span data-stu-id="d799a-161">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="d799a-162">Um die CLI unter macOS Sierra zu erstellen, müssen Sie die Umgebungsvariable DOTNET_RUNTIME_ID festlegen, indem Sie `export DOTNET_RUNTIME_ID=osx.10.11-x64` ausführen.</span><span class="sxs-lookup"><span data-stu-id="d799a-162">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="d799a-163">Verwenden Ihres Builds</span><span class="sxs-lookup"><span data-stu-id="d799a-163">Using your build</span></span>

<span data-ttu-id="d799a-164">Verwenden Sie die ausführbare Datei `dotnet` von *artifacts/{os}-{arch}/stage2*, um die neu erstellte CLI auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="d799a-164">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="d799a-165">Wenn Sie beim Aufrufen von `dotnet` aus der aktuellen Konsole die Buildausgabe verwenden möchten, können Sie auch *artifacts/{os}-{arch}/stage2* zum Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d799a-165">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="d799a-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d799a-166">See also</span></span>

* [<span data-ttu-id="d799a-167">.NET Core Common Language Runtime (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="d799a-167">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="d799a-168">.NET Core CLI Developer Guide (Entwicklerhandbuch für .NET Core-CLI)</span><span class="sxs-lookup"><span data-stu-id="d799a-168">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="d799a-169">.NET Core distribution packaging (Verpacken der Verteilung in .NET Core)</span><span class="sxs-lookup"><span data-stu-id="d799a-169">.NET Core distribution packaging</span></span>](./distribution-packaging.md)
