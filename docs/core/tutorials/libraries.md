---
title: Entwickeln von Bibliotheken mit der .NET Core-CLI
description: Erfahren Sie, wie Sie die .NET Core-CLI verwenden, um .NET-Bibliotheken zu erstellen. Sie erstellen damit eine Bibliothek, die mehrere Frameworks unterstützt.
author: cartermp
ms.topic: how-to
ms.date: 05/01/2017
ms.openlocfilehash: e98ce9e08c8d92bb4c89348e21cece60de811848
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223704"
---
# <a name="develop-libraries-with-the-net-core-cli"></a><span data-ttu-id="8bcb9-104">Entwickeln von Bibliotheken mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="8bcb9-104">Develop libraries with the .NET Core CLI</span></span>

<span data-ttu-id="8bcb9-105">Dieser Artikel erläutert, wie Sie mithilfe der .NET Core-CLI Bibliotheken für .NET schreiben.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-105">This article covers how to write libraries for .NET using the .NET Core CLI.</span></span> <span data-ttu-id="8bcb9-106">Die CLI bietet effiziente Funktionalität auf niedriger Stufe, die auf allen unterstützten Betriebssystemen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="8bcb9-107">Sie können trotzdem noch Bibliotheken mit Visual Studio erstellen. Wenn das Ihre bevorzugte Methode ist, finden Sie [weitere Informationen im Handbuch für Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](library-with-visual-studio.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8bcb9-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8bcb9-108">Prerequisites</span></span>

<span data-ttu-id="8bcb9-109">[Das .NET Core SDK und die CLI](https://dotnet.microsoft.com/download) müssen auf Ihrem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-109">You need [the .NET Core SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="8bcb9-110">Für die Abschnitte dieses Dokuments, in denen es um .NET Framework-Versionen geht, muss das [.NET Framework](https://dotnet.microsoft.com) auf einem Windows-Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="8bcb9-111">Wenn Sie ältere .NET Framework-Ziele unterstützen möchten, müssen Sie außerdem Pakete zum Festlegen von Zielversionen oder Entwicklerpakete von der Seite [.NET-Downloadarchive](https://dotnet.microsoft.com/download/archives) installieren.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting packs or developer packs from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="8bcb9-112">Weitere Informationen finden Sie in dieser Tabelle:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-112">Refer to this table:</span></span>

| <span data-ttu-id="8bcb9-113">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="8bcb9-113">.NET Framework version</span></span> | <span data-ttu-id="8bcb9-114">Empfohlene Downloads</span><span class="sxs-lookup"><span data-stu-id="8bcb9-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="8bcb9-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="8bcb9-115">4.6.1</span></span>                  | <span data-ttu-id="8bcb9-116">Paket zur Festlegung von Zielversionen für .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8bcb9-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="8bcb9-117">4.6</span><span class="sxs-lookup"><span data-stu-id="8bcb9-117">4.6</span></span>                    | <span data-ttu-id="8bcb9-118">Paket zur Festlegung von Zielversionen für .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8bcb9-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="8bcb9-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="8bcb9-119">4.5.2</span></span>                  | <span data-ttu-id="8bcb9-120">.NET Framework 4.5.2 Entwicklerpaket</span><span class="sxs-lookup"><span data-stu-id="8bcb9-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="8bcb9-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8bcb9-121">4.5.1</span></span>                  | <span data-ttu-id="8bcb9-122">.NET Framework 4.5.1 Entwicklerpaket</span><span class="sxs-lookup"><span data-stu-id="8bcb9-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="8bcb9-123">4.5</span><span class="sxs-lookup"><span data-stu-id="8bcb9-123">4.5</span></span>                    | <span data-ttu-id="8bcb9-124">Windows Software Development Kit für Windows 8</span><span class="sxs-lookup"><span data-stu-id="8bcb9-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="8bcb9-125">4,0</span><span class="sxs-lookup"><span data-stu-id="8bcb9-125">4.0</span></span>                    | <span data-ttu-id="8bcb9-126">Windows SDK für Windows 7 und .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="8bcb9-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="8bcb9-127">2.0, 3.0 und 3.5</span><span class="sxs-lookup"><span data-stu-id="8bcb9-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="8bcb9-128">.NET Framework 3.5 SP1-Runtime (oder Windows 8+-Version)</span><span class="sxs-lookup"><span data-stu-id="8bcb9-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-net-standard"></a><span data-ttu-id="8bcb9-129">Verwenden von .NET Standard als Ziel</span><span class="sxs-lookup"><span data-stu-id="8bcb9-129">How to target .NET Standard</span></span>

<span data-ttu-id="8bcb9-130">Wenn Sie noch nicht mit .NET Standard vertraut sind, finden Sie unter [.NET-Standard](../../standard/net-standard.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-130">If you're not familiar with .NET Standard, refer to [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="8bcb9-131">In diesem Artikel finden Sie eine Tabelle, in der die Versionen von .NET Standard zahlreichen Implementierungen zugeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-131">In that article, there is a table that maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

<span data-ttu-id="8bcb9-132">Im Folgenden wird erklärt, was diese Tabelle für das Erstellen einer Bibliothek bedeutet:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-132">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="8bcb9-133">Die Version von .NET Standard, die Sie auswählen, bildet einen Kompromiss zwischen dem Zugang zu den neuesten APIs und der Möglichkeit, mehr .NET-Implementierungen und .NET Standard-Versionen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-133">The version of .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="8bcb9-134">Sie kontrollieren den Bereich der Plattformen und der Versionen, die als Ziel festgelegt werden können, indem Sie eine Version von `netstandardX.X` auswählen (`X.X` steht für eine Versionsnummer) und sie Ihrer Projektdatei (`.csproj` oder `.fsproj`) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-134">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="8bcb9-135">Wenn Sie .NET Standard als Ziel festlegen, stehen Ihnen je nach Bedarf drei Optionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-135">You have three primary options when targeting .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="8bcb9-136">Sie können die Standardversion von .NET Standard verwenden, die durch Vorlagen (`netstandard1.4`) bereitgestellt wird. Dadurch erhalten Sie Zugriff auf die meisten APIs unter .NET Standard, wobei UWP, .NET Framework 4.6.1 und .NET Standard 2.0 noch immer kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-136">You can use the default version of .NET Standard supplied by templates, `netstandard1.4`, which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="8bcb9-137">Sie können eine niedrigere oder höhere Version von .NET Standard verwenden, indem Sie den Wert im `TargetFramework`-Knoten Ihrer Projektdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-137">You can use a lower or higher version of .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>

    <span data-ttu-id="8bcb9-138">.NET Standard-Versionen sind abwärtskompatibel.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-138">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="8bcb9-139">Das bedeutet, dass `netstandard1.0`-Bibliotheken auf `netstandard1.1`-Plattformen und höher ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-139">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="8bcb9-140">Es gibt jedoch keine Vorwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-140">However, there is no forward compatibility.</span></span> <span data-ttu-id="8bcb9-141">Frühere .NET Standard Plattformen-können nicht auf höhere Versionen verweisen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-141">Lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="8bcb9-142">Das bedeutet, dass `netstandard1.0`-Bibliotheken nicht auf Bibliotheken verweisen können, die `netstandard1.1` oder höher als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-142">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="8bcb9-143">Wählen Sie die Standard-Version aus, die die beste Mischung aus APIs und Plattformunterstützung für Ihre Anforderungen bietet.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-143">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="8bcb9-144">Wir empfehlen aktuell `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-144">We recommend `netstandard1.4` for now.</span></span>

3. <span data-ttu-id="8bcb9-145">Wenn Sie die .NET Framework-Version 4.0 oder niedriger als Ziel festlegen oder eine API verwenden möchten, die in .NET Framework verfügbar ist, aber nicht in .NET Standard (z. B. `System.Drawing`), lesen Sie die folgenden Abschnitte. In ihnen erfahren Sie, wie mehrere Ziele festlegt werden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-145">If you want to target .NET Framework versions 4.0 or below, or you wish to use an API available in .NET Framework but not in .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-net-framework"></a><span data-ttu-id="8bcb9-146">Vorgehensweise: .NET Framework als Ziel</span><span class="sxs-lookup"><span data-stu-id="8bcb9-146">How to target .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="8bcb9-147">In diesen Anleitungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-147">These instructions assume you have .NET Framework installed on your machine.</span></span> <span data-ttu-id="8bcb9-148">Informationen zum Installieren von Abhängigkeiten finden Sie unter [Erforderliche Komponenten](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-148">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="8bcb9-149">Bedenken Sie, dass einige der hier verwendeten .NET Framework-Versionen nicht mehr unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-149">Keep in mind that some of the .NET Framework versions used here are no longer supported.</span></span> <span data-ttu-id="8bcb9-150">Für weitere Informationen über nicht unterstütze Versionen, besuchen Sie [.NET Framework Support Lifecycle Policy FAQ (.NET Framework Support Lifecycle-Richtlinien FAQ)](https://support.microsoft.com/gp/framework_faq/en-us).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-150">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="8bcb9-151">Wenn Sie so viele Entwickler und Projekte erreichen möchten wie möglich, verwenden Sie .NET Framework 4.0 als Baselineziel.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-151">If you want to reach the maximum number of developers and projects, use .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="8bcb9-152">Um .NET Framework als Ziel festzulegen, müssen Sie zunächst den richtigen Zielframeworkmoniker (Target Framework Moniker, TMF) auswählen, der der .NET Framework-Version entspricht, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-152">To target .NET Framework, begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="8bcb9-153">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="8bcb9-153">.NET Framework version</span></span> | <span data-ttu-id="8bcb9-154">TFM</span><span class="sxs-lookup"><span data-stu-id="8bcb9-154">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="8bcb9-155">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="8bcb9-155">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="8bcb9-156">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="8bcb9-156">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="8bcb9-157">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="8bcb9-157">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="8bcb9-158">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="8bcb9-158">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="8bcb9-159">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8bcb9-159">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="8bcb9-160">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8bcb9-160">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="8bcb9-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8bcb9-161">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="8bcb9-162">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8bcb9-162">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="8bcb9-163">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8bcb9-163">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="8bcb9-164">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="8bcb9-164">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="8bcb9-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8bcb9-165">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="8bcb9-166">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="8bcb9-166">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="8bcb9-167">Sie fügen anschließend TFM in den `TargetFramework`-Abschnitt Ihrer Projektdatei ein.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-167">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="8bcb9-168">Hier sehen Sie zum Beispiel, wie Sie eine Bibliothek schreiben, die .NET Framework 4.0 als Ziel festlegt:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-168">For example, here's how you would write a library that targets .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="8bcb9-169">Das war’s!</span><span class="sxs-lookup"><span data-stu-id="8bcb9-169">And that's it!</span></span> <span data-ttu-id="8bcb9-170">Obwohl dieses Beispiel nur für .NET Framework 4 kompiliert wurde, können Sie die Bibliothek für neueren Versionen von .NET Framework verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-170">Although this compiled only for .NET Framework 4, you can use the library on newer versions of .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="8bcb9-171">Vorgehensweise: Festlegen mehrerer Ziele</span><span class="sxs-lookup"><span data-stu-id="8bcb9-171">How to multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="8bcb9-172">In den folgenden Anweisungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-172">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="8bcb9-173">Im Abschnitt [Erforderliche Komponenten](#prerequisites) finden Sie weitere Informationen darüber, welche Abhängigkeiten Sie installieren müssen, und wo Sie diese herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-173">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="8bcb9-174">Sie müssen möglicherweise ältere Versionen von .NET Framework als Ziel festlegen, wenn Ihr Projekt sowohl .NET Framework als auch .NET Core unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-174">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="8bcb9-175">Wenn Sie neuere APIs und Sprachkonstrukte für die neueren Ziele verwenden möchten, verwenden Sie in diesem Szenario `#if`-Anweisungen in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-175">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="8bcb9-176">Sie müssen möglicherweise auch unterschiedliche Pakete und Abhängigkeiten für jede Zielplattform hinzufügen, um verschiedene APIs einzuschließen, die für jeden Fall benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-176">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="8bcb9-177">Nehmen wir z.B. einmal an, dass Sie eine Bibliothek haben, die Netzwerkvorgänge über HTTP ausführt.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-177">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="8bcb9-178">Für .NET Standard und die .NET Framework-Versionen 4.5 oder höher können Sie die `HttpClient`-Klasse aus dem `System.Net.Http`-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-178">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="8bcb9-179">Frühere Versionen von .NET Framework verfügen jedoch nicht über die Klasse `HttpClient`, daher können Sie für diese stattdessen die Klasse `WebClient` aus dem Namespace `System.Net` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-179">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="8bcb9-180">Ihre Projektdatei könnte also Folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-180">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="8bcb9-181">Sie sehen hier drei große Veränderungen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-181">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="8bcb9-182">Der `TargetFramework`-Knoten wurde durch `TargetFrameworks` ersetzt, und drei TFMs werden darin dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-182">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="8bcb9-183">Es gibt einen `<ItemGroup>`-Knoten für das `net40`-Ziel, der einen .NET Framework-Verweis einbezieht.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-183">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="8bcb9-184">Es gibt einen `<ItemGroup>`-Knoten für das `net45`-Ziel, der zwei .NET Framework-Verweise einbezieht.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-184">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="8bcb9-185">Das Buildsystem beachtet die folgenden Präprozessorsymbole, die in `#if`-Anweisungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-185">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="8bcb9-186">Hier sehen sie ein Beispiel, das die bedingte Kompilierung pro Ziel verwendet:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-186">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="8bcb9-187">Wenn Sie diese Projekt mit `dotnet build` erstellen, bemerken Sie drei Verzeichnisse unter dem `bin/`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-187">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="8bcb9-188">Jedes dieser Verzeichnisse enthält die `.dll`-Dateien für jedes Ziel.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-188">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="8bcb9-189">So testen Sie die Bibliotheken unter .NET Core</span><span class="sxs-lookup"><span data-stu-id="8bcb9-189">How to test libraries on .NET Core</span></span>

<span data-ttu-id="8bcb9-190">Es ist wichtig, über Plattformen hinweg testen zu können.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-190">It's important to be able to test across platforms.</span></span> <span data-ttu-id="8bcb9-191">Sie können entweder [xUnit](https://xunit.github.io/) oder MSTest standardmäßig verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-191">You can use either [xUnit](https://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="8bcb9-192">Beide sind bestens für Komponententests für Ihre Bibliothek unter .NET Core geeignet.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-192">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="8bcb9-193">Wie Sie Ihre Lösung mit Testprojekten einrichten, hängt von der [Struktur Ihrer Lösung](#structuring-a-solution) ab.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-193">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="8bcb9-194">Im folgenden Beispiel wird davon ausgegangen, dass Test- und Quellverzeichnisse im gleichen Verzeichnis auf oberster Ebene vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-194">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="8bcb9-195">Es werden einige [.NET Core-CLI](../tools/index.md)-Befehle verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-195">This uses some [.NET Core CLI](../tools/index.md) commands.</span></span> <span data-ttu-id="8bcb9-196">Weitere Informationen finden Sie unter [dotnet new](../tools/dotnet-new.md) und [dotnet sln](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-196">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="8bcb9-197">Richten Sie Ihre Projektmappe ein.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-197">Set up your solution.</span></span> <span data-ttu-id="8bcb9-198">Verwenden Sie dazu folgende Befehle:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-198">You can do so with the following commands:</span></span>

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="8bcb9-199">Dadurch werden Projekte erstellt, die zusammen in einer Projektmappe verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-199">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="8bcb9-200">Ihr Verzeichnis für `SolutionWithSrcAndTest` sollte in etwa so aussehen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-200">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="8bcb9-201">Navigieren Sie zum Verzeichnis des Testprojekts, und fügen Sie einen Verweis zu `MyProject.Test` von `MyProject` hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-201">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="8bcb9-202">So stellen Sie Pakete wieder her und erstellen Projekte:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-202">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. <span data-ttu-id="8bcb9-203">Überprüfen Sie, ob xUnit durch Ausführung des `dotnet test`-Befehls ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-203">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="8bcb9-204">Wenn Sie MSTests verwenden möchten, dann muss stattdessen das MSTest-Konsolenausführungsprogramm ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-204">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="8bcb9-205">Das war’s!</span><span class="sxs-lookup"><span data-stu-id="8bcb9-205">And that's it!</span></span> <span data-ttu-id="8bcb9-206">Jetzt können Sie Ihre Bibliothek mithilfe der Befehlszeilentools plattformübergreifend testen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-206">You can now test your library across all platforms using command-line tools.</span></span> <span data-ttu-id="8bcb9-207">Nachdem jetzt alles eingerichtet ist, ist das weitere Testen Ihrer Bibliothek sehr einfach:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-207">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="8bcb9-208">Nehmen Sie Änderungen an Ihrer Bibliothek vor.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-208">Make changes to your library.</span></span>
1. <span data-ttu-id="8bcb9-209">Führen Sie mit dem Befehl `dotnet test` in Ihrem Testverzeichnis Tests über die Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-209">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="8bcb9-210">Der Code wird automatisch neu erstellt, wenn Sie den Befehl `dotnet test` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-210">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="8bcb9-211">So verwenden Sie mehrere Projekte</span><span class="sxs-lookup"><span data-stu-id="8bcb9-211">How to use multiple projects</span></span>

<span data-ttu-id="8bcb9-212">Eine häufige Anforderung an größere Bibliotheken ist es, Funktionalität in verschiedenen Projekten zu bieten.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-212">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="8bcb9-213">Stellen Sie sich vor, Sie möchten eine Bibliothek erstellen, die in idiomatischem C# und F# genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-213">Imagine you want to build a library that could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="8bcb9-214">Das würde bedeuten, dass Benutzer Ihrer Bibliotheken diese auf eine Art nutzen, die natürlich für C# und F# ist.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-214">That would mean that consumers of your library consume it in ways that are natural to C# or F#.</span></span> <span data-ttu-id="8bcb9-215">In C# z.B. könnten Sie die Bibliothek wie folgt nutzen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-215">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="8bcb9-216">In F# wird wie folgt formuliert:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-216">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="8bcb9-217">Solche Nutzungsszenarios bedeuten, dass die APIs, auf die zugegriffen wird, eine andere Struktur für C# und F# haben müssen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-217">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="8bcb9-218">Eine gängige Methode, dies zu erreichen ist, die gesamte Logik einer Bibliothek in ein Kernprojekt zu zerlegen, in dem C# und F# Projekte die API-Schichten definieren, die das Kernprojekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-218">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="8bcb9-219">Im übrigen Abschnitt werden die folgenden Namen verwendet:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-219">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="8bcb9-220">**AwesomeLibrary.Core** – Ein Kernprojekt, das die gesamte Logik für die Bibliothek enthält</span><span class="sxs-lookup"><span data-stu-id="8bcb9-220">**AwesomeLibrary.Core** - A core project that contains all logic for the library</span></span>
* <span data-ttu-id="8bcb9-221">**AwesomeLibrary.CSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in C# vorgesehen sind</span><span class="sxs-lookup"><span data-stu-id="8bcb9-221">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="8bcb9-222">**AwesomeLibrary.FSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in F# vorgesehen sind</span><span class="sxs-lookup"><span data-stu-id="8bcb9-222">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="8bcb9-223">Sie können die folgenden Befehle in Ihrem Terminal ausführen, um die gleiche Struktur wie dieses Handbuch zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-223">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="8bcb9-224">Dadurch werden die drei oben genannten Projekte und eine Projektmappendatei hinzugefügt, die sie verknüpft.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-224">This will add the three projects above and a solution file that links them together.</span></span> <span data-ttu-id="8bcb9-225">Durch das Erstellen der Projektmappendatei und das Verknüpfen der Projekte können Sie Projekte auf oberster Ebene wiederherstellen und erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-225">Creating the solution file and linking projects will allow you to restore and build projects from a top level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="8bcb9-226">Projekt-zu-Projekt-Verweise</span><span class="sxs-lookup"><span data-stu-id="8bcb9-226">Project-to-project referencing</span></span>

<span data-ttu-id="8bcb9-227">Die beste Möglichkeit, auf ein Projekt zu verweisen, ist die Verwendung der .NET Core-CLI, um einen Projektverweis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-227">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="8bcb9-228">Sie können den folgenden Befehl von den Projektverzeichnissen **AwesomeLibrary.CSharp** und **AwesomeLibrary.FSharp** ausführen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-228">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="8bcb9-229">Die Projektdateien für **AwesomeLibrary.CSharp** und **AwesomeLibrary.FSharp** verweisen nun auf **AwesomeLibrary.Core** als `ProjectReference`-Ziel.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-229">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="8bcb9-230">Sie können dies überprüfen, indem Sie die Projektdateien prüfen und Folgendes darin sehen:</span><span class="sxs-lookup"><span data-stu-id="8bcb9-230">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="8bcb9-231">Sie können diesen Abschnitt jeder Projektdatei manuell hinzufügen, wenn Sie nicht die .NET Core-CLI verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-231">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="8bcb9-232">Strukturieren einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="8bcb9-232">Structuring a solution</span></span>

<span data-ttu-id="8bcb9-233">Ein weiterer wichtiger Aspekt bei mehreren Projekten in einer Projektmappe ist es, eine gute allgemeine Projektstruktur einzurichten.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-233">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="8bcb9-234">Sie können den Code beliebig organisieren, solange Sie jedes Projekt mit Ihrer Projektmappendatei mit `dotnet sln add` verknüpfen. Dadurch können Sie `dotnet restore` und `dotnet build` auf Projektmappenebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-234">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
