---
title: .NET Core-CLI-Erweiterbarkeitsmodell
description: Erfahren Sie, wie Sie die .NET Core-CLI erweitern können.
ms.date: 04/12/2017
ms.openlocfilehash: 56a9cedc090ddca446c0ee1a60f2ca49590e7635
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451154"
---
# <a name="net-core-cli-extensibility-model"></a><span data-ttu-id="c77a5-103">.NET Core-CLI-Erweiterbarkeitsmodell</span><span class="sxs-lookup"><span data-stu-id="c77a5-103">.NET Core CLI extensibility model</span></span>

<span data-ttu-id="c77a5-104">In diesem Artikel werden die unterschiedlichen Möglichkeiten vorgestellt, mit denen Sie die .NET Core-CLI erweitern können, und es werden die Szenarien erläutert, in denen diese jeweils genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-104">This article covers the different ways you can extend the .NET Core CLI and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="c77a5-105">Sie sehen, wie Sie die Tools verarbeiten und wie unterschiedliche Typen von Tools erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="c77a5-105">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-the-cli"></a><span data-ttu-id="c77a5-106">Erweitern der CLI</span><span class="sxs-lookup"><span data-stu-id="c77a5-106">How to extend the CLI</span></span>
<span data-ttu-id="c77a5-107">Die CLI kann auf drei Arten erweitert werden:</span><span class="sxs-lookup"><span data-stu-id="c77a5-107">The CLI can be extended in three main ways:</span></span>

1. [<span data-ttu-id="c77a5-108">Projektweise über NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="c77a5-108">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

   <span data-ttu-id="c77a5-109">Die projektbezogenen Tools sind im Kontext des Projekts enthalten, aber sie ermöglichen eine einfache Installation über die Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="c77a5-109">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="c77a5-110">Über NuGet-Pakete mit benutzerdefinierten Zielen</span><span class="sxs-lookup"><span data-stu-id="c77a5-110">Via NuGet packages with custom targets</span></span>](#custom-targets)

   <span data-ttu-id="c77a5-111">Mithilfe benutzerdefinierter Ziele können Sie den Buildprozess einfach mit benutzerdefinierten Aufgaben erweitern.</span><span class="sxs-lookup"><span data-stu-id="c77a5-111">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="c77a5-112">Über die Systemvariable PATH</span><span class="sxs-lookup"><span data-stu-id="c77a5-112">Via the system's PATH</span></span>](#path-based-extensibility)

   <span data-ttu-id="c77a5-113">Auf PATH basierende Tools eignen sich für allgemeine projektübergreifende Tools, die auf einem einzelnen Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-113">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="c77a5-114">Die drei oben beschriebenen Erweiterbarkeitsmechanismen schließen sich nicht gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="c77a5-114">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="c77a5-115">Sie können beide oder nur einen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-115">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="c77a5-116">Welchen Sie auswählen, hängt größtenteils davon ab, welches Ziel Sie mit der Erweiterung erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="c77a5-116">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="c77a5-117">Projektbezogene Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="c77a5-117">Per-project based extensibility</span></span>
<span data-ttu-id="c77a5-118">Projektbezogene Tools sind [frameworkabhängige Bereitstellungen](../deploying/index.md#publish-runtime-dependent), die als NuGet-Pakete verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-118">Per-project tools are [framework-dependent deployments](../deploying/index.md#publish-runtime-dependent) that are distributed as NuGet packages.</span></span> <span data-ttu-id="c77a5-119">Tools sind nur im Kontext des Projekts verfügbar, das auf sie verweist und für das sie gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c77a5-119">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="c77a5-120">Ein Aufruf außerhalb des Projektkontexts (z.B. außerhalb des Verzeichnisses, das das Projekt enthält) schlägt fehl, da der Befehl nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="c77a5-120">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="c77a5-121">Diese Tools sind ideal für Buildserver, da nichts außer der Projektdatei erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c77a5-121">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="c77a5-122">Der Buildprozess führt die Wiederherstellung für das Projekt, das es erstellt, aus, und die Tools stehen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c77a5-122">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="c77a5-123">Sprachprojekte, wie F#, befinden sich auch in dieser Kategorie, da jedes Projekt nur in einer bestimmten Sprache geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="c77a5-123">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="c77a5-124">Schließlich bietet dieses Erweiterbarkeitsmodell Unterstützung für die Erstellung von Tools, die Zugriff auf die Buildausgabe des Projekts benötigen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-124">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="c77a5-125">Verschiedene Razor-Ansicht-Tools in [ASP.NET](https://www.asp.net/)-MVC-Anwendungen fallen z.B. in diese Kategorie.</span><span class="sxs-lookup"><span data-stu-id="c77a5-125">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="c77a5-126">Tools pro Projekt verwenden</span><span class="sxs-lookup"><span data-stu-id="c77a5-126">Consuming per-project tools</span></span>
<span data-ttu-id="c77a5-127">Zum Nutzen dieser Tools müssen Sie das Element `<DotNetCliToolReference>` für jedes Tool hinzufügen, das Sie der Projektdatei verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c77a5-127">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="c77a5-128">Im Element `<DotNetCliToolReference>` verweisen Sie auf das Paket, in dem sich das Tool befindet, und geben die Version an, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-128">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="c77a5-129">Nach der Ausführung von [`dotnet restore`](dotnet-restore.md) werden das Tool und die zugehörigen Abhängigkeiten wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c77a5-129">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c77a5-130">Für Tools, die die Buildausgabe des Projekts zur Ausführung laden müssen, gibt es normalerweise eine andere Abhängigkeit, die unter den regulären Abhängigkeiten in der Projektdatei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c77a5-130">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="c77a5-131">Da die CLI als Build-Engine MSBuild verwendet, wird empfohlen, diese Teile des Tools als benutzerdefinierte MSBuild-[Ziele](/visualstudio/msbuild/msbuild-targets) und -[Aufgaben](/visualstudio/msbuild/msbuild-tasks) zu schreiben, da sie auf diese Weise am gesamten Buildprozess teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c77a5-131">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="c77a5-132">Außerdem können sie mühelos sämtliche Daten abrufen, die über den Build erstellt werden, z.B. den Speicherort der Ausgabedateien, die aktuell erstellte Konfiguration usw.</span><span class="sxs-lookup"><span data-stu-id="c77a5-132">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, and so on.</span></span> <span data-ttu-id="c77a5-133">Alle diese Informationen bilden eine Gruppe von MSBuild-Eigenschaften, die von jedem beliebigen Ziel gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="c77a5-133">All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="c77a5-134">Weiter unten in diesem Dokument erfahren Sie, wie über NuGet ein benutzerdefiniertes Ziel hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c77a5-134">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="c77a5-135">Betrachten wir ein Beispiel, bei dem ein Tools-Only-Tool zu einem einfachen Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c77a5-135">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="c77a5-136">Für einen Beispielbefehl namens `dotnet-api-search`, mit dem Sie die NuGet-Pakete nach der angegebenen API durchsuchen können, sehen Sie hier die Projektdatei einer Konsolenanwendung, die dieses Tool verwendet:</span><span class="sxs-lookup"><span data-stu-id="c77a5-136">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="c77a5-137">Das Element `<DotNetCliToolReference>` weist eine ähnliche Struktur auf wie das Element `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="c77a5-137">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="c77a5-138">Er benötigt die Paket-ID des Pakets mit dem Tool und dessen Version, damit ein Wiederherstellungsvorgang ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c77a5-138">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="c77a5-139">Erstellen von Tools</span><span class="sxs-lookup"><span data-stu-id="c77a5-139">Building tools</span></span>
<span data-ttu-id="c77a5-140">Wie bereits erwähnt, sind Tools nur portable Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-140">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="c77a5-141">Sie würden ein Tool erstellen, so wie Sie alle Konsolenanwendungen erstellen würden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-141">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="c77a5-142">Nachdem Sie es erstellt haben, führen Sie den [`dotnet pack`](dotnet-pack.md)-Befehl aus, um ein NuGet-Paket (NUPKG-Datei) zu erstellen, das Ihren Code, die Informationen zu seinen Abhängigkeiten usw. enthält.</span><span class="sxs-lookup"><span data-stu-id="c77a5-142">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="c77a5-143">Die können den Paketnamen benennen, aber die Anwendung darin, das tatsächliche Binär-Tool, muss der `dotnet-<command>`-Konvention entsprechen, damit `dotnet` es aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="c77a5-143">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="c77a5-144">In Versionen der .NET Core-Befehlszeilentools vor RC3 hatte der Befehl `dotnet pack` einen Fehler, der dazu führte, dass die Datei *.runtimeconfig.json* nicht mit dem Tool gepackt wurde.</span><span class="sxs-lookup"><span data-stu-id="c77a5-144">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the *.runtimeconfig.json* to not be packed with the tool.</span></span> <span data-ttu-id="c77a5-145">Fehlt diese Datei, treten zur Laufzeit Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c77a5-145">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="c77a5-146">Wenn dieses Verhalten auftritt, sollten Sie auf die neuesten Tools aktualisieren und erneut versuchen, den Befehl `dotnet pack` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-146">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="c77a5-147">Da Tools portable Anwendungen sind, muss der Benutzer des Tools über die Version der .NET Core-Bibliotheken verfügen, für die das Tool entwickelt wurde, um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-147">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="c77a5-148">Jede andere Abhängigkeit, die das Tool verwendet und nicht in den .NET Core-Bibliotheken enthalten ist, wird wiederhergestellt und im NuGet-Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c77a5-148">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="c77a5-149">Das gesamte Tool wird daher mithilfe der Assemblys aus den .NET Core-Bibliotheken sowie Assemblys aus dem NuGet-Cache ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c77a5-149">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="c77a5-150">Diese Art von Tools haben ein Abhängigkeitsdiagramm, das komplett unabhängig ist vom Abhängigkeitsdiagramm des Projekts, welches sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c77a5-150">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="c77a5-151">Der Wiederherstellungsvorgang wird zuerst die Projektabhängigkeiten wiederherstellen und dann jedes der Tools und deren Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="c77a5-151">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="c77a5-152">Umfangreichere Beispiele und verschiedene Kombinationen dessen finden Sie im [.NET Core-CLI-Repository](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span><span class="sxs-lookup"><span data-stu-id="c77a5-152">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="c77a5-153">Sie finden auch die [Implementierung von verwendeten Tools](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) im gleichen Repository.</span><span class="sxs-lookup"><span data-stu-id="c77a5-153">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) in the same repo.</span></span>

## <a name="custom-targets"></a><span data-ttu-id="c77a5-154">Benutzerdefinierte Ziele</span><span class="sxs-lookup"><span data-stu-id="c77a5-154">Custom targets</span></span>

<span data-ttu-id="c77a5-155">NuGet kann [benutzerdefinierte MSBuild-Ziele und PROPS-Dateien packen](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="c77a5-155">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="c77a5-156">Seit .NET Core MSBuild verwendet, gilt derselbe Erweiterbarkeitsmechanismus auch für .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="c77a5-156">With the move of the .NET Core to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="c77a5-157">Sie nutzen diese Art von Erweiterbarkeit, wenn Sie den Buildprozess erweitern möchten, im Buildprozess auf Artefakte wie generierte Dateien zugreifen oder die Konfiguration überprüfen möchten, in der der Build aufgerufen wird usw.</span><span class="sxs-lookup"><span data-stu-id="c77a5-157">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, and so on.</span></span>

<span data-ttu-id="c77a5-158">Im folgenden Beispiel können Sie die Projektdatei des Ziels mithilfe der `csproj`-Syntax anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-158">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="c77a5-159">Dies zeigt dem [`dotnet pack`](dotnet-pack.md)-Befehl, was genau gepackt werden soll, wobei die Zieldateien sowie die Assemblys in den Ordner *Erstellen* im Paket platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-159">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="c77a5-160">Beachten Sie das `<ItemGroup>`-Element, das über die Eigenschaft `Label` verfügt, die auf `dotnet pack instructions` festgelegt ist, sowie das Ziel, das darunter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c77a5-160">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c77a5-161">Die Nutzung benutzerdefinierter Ziele erfolgt durch Bereitstellung einer `<PackageReference>`, die auf ein Paket und dessen Version innerhalb des Projekts verweist, das erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="c77a5-161">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="c77a5-162">Im Gegensatz zu den Tools wird das benutzerdefinierte Zielpaket in die Hülle der Abhängigkeiten des nutzenden Projekts eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-162">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="c77a5-163">Die Verwendung des benutzerdefinierten Ziels hängt ausschließlich von seiner Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="c77a5-163">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="c77a5-164">Da dies ein MSBuild-Ziel ist, kann es von einem angegebenen Ziel abhängen, nach einem anderen Ziel ausgeführt werden und mit dem Befehl `dotnet msbuild -t:<target-name>` auch manuell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-164">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild -t:<target-name>` command.</span></span>

<span data-ttu-id="c77a5-165">Wenn Sie jedoch Ihren Benutzern eine bessere Erfahrung bieten möchten, können Sie projektbezogene Tools und benutzerdefinierte Ziele kombinieren.</span><span class="sxs-lookup"><span data-stu-id="c77a5-165">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="c77a5-166">In diesem Szenario akzeptiert das projektbezogene Tool lediglich die benötigten Parameter, die in den erforderlichen Aufruf von [`dotnet msbuild`](dotnet-msbuild.md) übersetzt werden, über den das Ziel ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c77a5-166">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="c77a5-167">Sie sehen ein Beispiel dieser Art von Synergie im Repository mit den [MVP Summit 2016 Hackathon-Beispielen](https://github.com/dotnet/MVPSummitHackathon2016) im Projekt [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="c77a5-167">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="path-based-extensibility"></a><span data-ttu-id="c77a5-168">PFAD-basierte Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="c77a5-168">PATH-based extensibility</span></span>
<span data-ttu-id="c77a5-169">Die PFAD-basierte Erweiterbarkeit wird in der Regel für Entwicklungscomputer verwendet, bei denen Sie ein Tool brauchen, das konzeptionell mehr als ein einzelnes Projekt abdeckt.</span><span class="sxs-lookup"><span data-stu-id="c77a5-169">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="c77a5-170">Der größte Nachteil dieses Extensionsmechanismus ist, dass es mit dem Computer verknüpft ist, auf dem das Tool existiert.</span><span class="sxs-lookup"><span data-stu-id="c77a5-170">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="c77a5-171">Wenn Sie ihn auf einem anderen Computer benötigen, müssten Sie ihn bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-171">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="c77a5-172">Dieses Muster der Erweiterbarkeit des CLI-Toolsets ist sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="c77a5-172">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="c77a5-173">Wie in der [Übersicht über die .NET Core-CLI](index.md) beschrieben, kann der `dotnet`-Treiber jeden Befehl ausführen, der nach der `dotnet-<command>`-Konvention benannt ist.</span><span class="sxs-lookup"><span data-stu-id="c77a5-173">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="c77a5-174">Die Standardauflösungslogik wird zuerst mehrere Speicherorte überprüfen und schließlich an den SYSTEMPFAD fallen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-174">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="c77a5-175">Wenn der angeforderte Befehl im SYSTEMPFAD vorhanden und eine Binärdatei ist, die aufgerufen werden kann, wird sie der `dotnet`-Treiber aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-175">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="c77a5-176">Bei der Datei muss es sich um eine ausführbare Datei handeln.</span><span class="sxs-lookup"><span data-stu-id="c77a5-176">The file must be executable.</span></span> <span data-ttu-id="c77a5-177">Auf Unix-Systemen bedeutet dies alles, das das ausführbare Bit über `chmod +x` festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="c77a5-177">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="c77a5-178">Unter Windows können Sie *CMD*-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-178">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="c77a5-179">Sehen wir uns nun die einfache Implementierung eines „Hello World“-Tools an.</span><span class="sxs-lookup"><span data-stu-id="c77a5-179">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="c77a5-180">Wir verwenden jeweils `bash` und `cmd` unter Windows.</span><span class="sxs-lookup"><span data-stu-id="c77a5-180">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="c77a5-181">Der folgende Befehl liefert einfach „Hello World“ an die Konsole.</span><span class="sxs-lookup"><span data-stu-id="c77a5-181">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="c77a5-182">Auf Mac OS können wir dieses Skript als `dotnet-hello` speichern und sein ausführbares Bit mit `chmod +x dotnet-hello` festlegen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-182">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="c77a5-183">Wir erstellen dann eine symbolische Verknüpfung in `/usr/local/bin` mit dem Befehl `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span><span class="sxs-lookup"><span data-stu-id="c77a5-183">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="c77a5-184">So kann der Befehl mit der `dotnet hello`-Syntax aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c77a5-184">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="c77a5-185">Wir können unter Windows das Skript als `dotnet-hello.cmd` speichern und es an einem Speicherort speichern, der sich in einem Systempfad befindet (oder Sie können es einem Ordner hinzufügen, der sich bereits im Pfad befindet).</span><span class="sxs-lookup"><span data-stu-id="c77a5-185">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="c77a5-186">Verwenden Sie danach einfach `dotnet hello`, um dieses Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c77a5-186">After this, you can just use `dotnet hello` to run this example.</span></span>
