---
title: Beispiel für die Migration zu .NET Core 3.1
description: Es wird gezeigt, wie Sie eine Beispielanwendung, die .NET Framework, auf .net Core 3,1 migrieren.
ms.date: 05/12/2020
ms.openlocfilehash: dc0d3d825847bd72a38469615cfc5b2d793f1977
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188776"
---
# <a name="example-of-migrating-to-net-core-31"></a><span data-ttu-id="e667f-103">Beispiel für die Migration zu .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="e667f-103">Example of migrating to .NET Core 3.1</span></span>

<span data-ttu-id="e667f-104">In diesem Kapitel werden praktische Richtlinien vorgestellt, die Ihnen bei der Migration Ihrer vorhandenen Anwendung von .NET Framework zu .net Core helfen.</span><span class="sxs-lookup"><span data-stu-id="e667f-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET Core.</span></span>

<span data-ttu-id="e667f-105">Wir präsentieren einen gut strukturierten Prozess, den Sie befolgen können, und die wichtigsten Punkte, die bei jedem Schritt berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e667f-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="e667f-106">Anschließend wird ein schrittweises Migrationsverfahren für eine Beispiel-Desktop Anwendung, beides aus WinForms-und WPF-Versionen, dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="e667f-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="e667f-107">Übersicht über den Migrationsprozess</span><span class="sxs-lookup"><span data-stu-id="e667f-107">Migration process overview</span></span>

<span data-ttu-id="e667f-108">Der Migrations Vorgang besteht aus vier aufeinander folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="e667f-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="e667f-109">**Vorbereitung**: verstehen Sie die Abhängigkeiten des Projekts, um eine Vorstellung davon zu erhalten, was vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="e667f-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="e667f-110">In diesem Schritt nehmen Sie das aktuelle Projekt in einen Zustand, der den Startpunkt für die Migration vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e667f-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="e667f-111">**Projektdatei migrieren:** für .net Core-Projekte wird das neue Projekt Format im SDK-Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="e667f-111">**Migrate Project File:** .NET Core projects use the new SDK-style project format.</span></span> <span data-ttu-id="e667f-112">Erstellen Sie eine neue Projektdatei mit diesem Format, oder aktualisieren Sie die Datei, für die Sie den SDK-Stil verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e667f-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="e667f-113">**Korrigieren Sie den Code und den Build:** Erstellen Sie den Code in .net Core, der die Unterschiede auf API-Ebene zwischen .NET Framework und .net Core adressiert.</span><span class="sxs-lookup"><span data-stu-id="e667f-113">**Fix code and build:** Build the code in .NET Core addressing API-level differences between .NET Framework and .NET Core.</span></span> <span data-ttu-id="e667f-114">Aktualisieren Sie bei Bedarf Pakete von Drittanbietern auf diejenigen, die .net Core unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e667f-114">If needed, update third-party packages to the ones that support .NET Core.</span></span>

4. <span data-ttu-id="e667f-115">**Ausführen und testen:** Möglicherweise gibt es Unterschiede, die bis zur Laufzeit nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e667f-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="e667f-116">Vergessen Sie daher nicht, die Anwendung auszuführen und zu testen, ob alles erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e667f-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="e667f-117">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="e667f-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="e667f-118">Migrieren packages.config Datei</span><span class="sxs-lookup"><span data-stu-id="e667f-118">Migrate packages.config file</span></span>

<span data-ttu-id="e667f-119">In einer .NET Framework Anwendung werden alle Verweise auf externe Pakete in der *packages.config* -Datei deklariert.</span><span class="sxs-lookup"><span data-stu-id="e667f-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="e667f-120">In .net Core ist es nicht mehr erforderlich, die *packages.config* -Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e667f-120">In .NET Core, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="e667f-121">Verwenden Sie stattdessen die [packagereferenzierungseigenschaft](../../core/project-sdk/msbuild-props.md#packagereference) in der Projektdatei, um die nuget-Pakete für Ihre APP anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e667f-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="e667f-122">Daher müssen Sie von einem Format in ein anderes wechseln.</span><span class="sxs-lookup"><span data-stu-id="e667f-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="e667f-123">Sie können das Update manuell ausführen, indem Sie die in der *packages.config* -Datei enthaltenen Abhängigkeiten übernehmen und Sie in die Projektdatei mit dem `PackageReference` Format migrieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="e667f-124">Alternativ können Sie Visual Studio für Sie ausführen lassen: Klicken Sie mit der rechten Maustaste auf die Datei *packages.config* , und wählen Sie die Option **packages.config zu packagereferenzierung migrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e667f-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net-core"></a><span data-ttu-id="e667f-125">Überprüfen aller Abhängigkeits Kompatibilität in .net Core</span><span class="sxs-lookup"><span data-stu-id="e667f-125">Verify every dependency compatibility in .NET Core</span></span>

<span data-ttu-id="e667f-126">Nachdem Sie die Paket Verweise migriert haben, müssen Sie jeden Verweis auf Kompatibilität überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e667f-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="e667f-127">Sie können die Abhängigkeiten der einzelnen nuget-Pakete untersuchen, die Ihre Anwendung auf [nuget.org](https://www.nuget.org/)verwendet. Wenn das Paket .NET Standard Abhängigkeiten aufweist, wird es auf .net Core funktionieren, da .net Core 3,1 alle Versionen von .NET Standard [unterstützt](../../standard/net-standard.md#net-implementation-support) .</span><span class="sxs-lookup"><span data-stu-id="e667f-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET Core because .NET Core 3.1 [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="e667f-128">Die folgende Abbildung zeigt die Abhängigkeiten für das `Castle.Windsor` Paket:</span><span class="sxs-lookup"><span data-stu-id="e667f-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Screenshot der nuget-Abhängigkeiten für das Castle. Windsor-Paket](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="e667f-130">Zum Überprüfen der Paket Kompatibilität können Sie das Tool verwenden <https://fuget.org> , das ausführlichere Informationen zu Versionen und Abhängigkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="e667f-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="e667f-131">Möglicherweise verweist das Projekt auf ältere Paketversionen, die .net Core nicht unterstützen, aber Sie finden neuere Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e667f-131">Maybe the project is referencing older package versions that don't support .NET Core, but you might find newer versions that do support it.</span></span> <span data-ttu-id="e667f-132">Das Aktualisieren von Paketen auf neuere Versionen ist im Allgemeinen eine gute Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="e667f-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="e667f-133">Sie sollten jedoch berücksichtigen, dass durch die Aktualisierung der Paketversion einige wichtige Änderungen eingeführt werden, die das Aktualisieren Ihres Codes erzwingen würden.</span><span class="sxs-lookup"><span data-stu-id="e667f-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="e667f-134">Was geschieht, wenn Sie keine kompatible Version finden?</span><span class="sxs-lookup"><span data-stu-id="e667f-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="e667f-135">Was geschieht, wenn Sie die Version eines Pakets aufgrund dieser wichtigen Änderungen nicht aktualisieren möchten?</span><span class="sxs-lookup"><span data-stu-id="e667f-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="e667f-136">Keine Sorge, da es möglich ist, von einer .net Core-Anwendung aus .NET Framework Paketen zu abhängen.</span><span class="sxs-lookup"><span data-stu-id="e667f-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET Core application.</span></span> <span data-ttu-id="e667f-137">Vergessen Sie nicht, Sie ausgiebig zu testen, da Sie Laufzeitfehler verursachen kann, wenn das externe Paket eine API aufruft, die in .net Core nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e667f-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET Core.</span></span> <span data-ttu-id="e667f-138">Dies eignet sich hervorragend für den Fall, dass Sie ein altes Paket verwenden, das nicht aktualisiert wird, und Sie können einfach neu zuweisen, um auf .net Core zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e667f-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET Core.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="e667f-139">Auf API-Kompatibilität überprüfen</span><span class="sxs-lookup"><span data-stu-id="e667f-139">Check for API compatibility</span></span>

<span data-ttu-id="e667f-140">Da die API-Oberfläche in .NET Framework und .net Core ähnlich, aber nicht identisch ist, müssen Sie überprüfen, welche APIs in .net Core verfügbar sind und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="e667f-140">Since the API surface in .NET Framework and .NET Core is similar but not identical, you must check which APIs are available on .NET Core and which aren't.</span></span> <span data-ttu-id="e667f-141">Sie können das Tool .net-Portabilitäts Analyse verwenden, um APIs zu verwenden, die nicht in .net Core vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e667f-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET Core.</span></span> <span data-ttu-id="e667f-142">Sie untersucht die binäre Ebene Ihrer APP, extrahiert alle APIs, die aufgerufen werden, und listet dann auf, welche APIs in Ihrem Ziel Framework nicht verfügbar sind (in diesem Fall .net Core 3,1).</span><span class="sxs-lookup"><span data-stu-id="e667f-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET Core 3.1 in this case).</span></span>

<span data-ttu-id="e667f-143">Weitere Informationen zu diesem Tool finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e667f-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="e667f-144">Ein interessanter Aspekt dieses Tools besteht darin, dass nur die Unterschiede von Ihrem eigenen Code und nicht von Code aus externen Paketen, die Sie nicht ändern können, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e667f-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="e667f-145">Denken Sie daran, dass Sie die meisten dieser Pakete aktualisiert haben müssen, damit Sie mit .net Core funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-145">Remember you should have updated most of these packages to make them work with .NET Core.</span></span>

### <a name="migrate-project-file"></a><span data-ttu-id="e667f-146">Projektdatei migrieren</span><span class="sxs-lookup"><span data-stu-id="e667f-146">Migrate project file</span></span>

#### <a name="create-the-new-net-core-project"></a><span data-ttu-id="e667f-147">Erstellen des neuen .net Core-Projekts</span><span class="sxs-lookup"><span data-stu-id="e667f-147">Create the new .NET Core project</span></span>

<span data-ttu-id="e667f-148">In den meisten Fällen sollten Sie Ihr vorhandenes Projekt auf das neue .net Core-Format aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-148">In most of the cases, you'll want to update your existing project to the new .NET Core format.</span></span> <span data-ttu-id="e667f-149">Sie können jedoch auch ein neues Projekt erstellen, während Sie das alte Projekt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e667f-149">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="e667f-150">Der Hauptnachteil beim Aktualisieren des alten Projekts ist, dass Sie die Designer Unterstützung verlieren, was für Sie wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="e667f-150">The main drawback from updating the old project is that you lose designer support, which may be important for you.</span></span> <span data-ttu-id="e667f-151">Wenn Sie den Designer weiterhin verwenden möchten, müssen Sie ein neues .net Core-Projekt parallel zum alten erstellen und Assets freigeben.</span><span class="sxs-lookup"><span data-stu-id="e667f-151">If you want to keep using the designer, you must create a new .NET Core project in parallel with the old one and share assets.</span></span> <span data-ttu-id="e667f-152">Wenn Sie Benutzeroberflächen Elemente im Designer ändern müssen, können Sie dazu zum alten Projekt wechseln.</span><span class="sxs-lookup"><span data-stu-id="e667f-152">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="e667f-153">Und da Assets verknüpft sind, werden Sie ebenfalls im .net Core-Projekt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e667f-153">And since assets are linked, they'll be updated in the .NET Core project as well.</span></span>

<span data-ttu-id="e667f-154">Das [SDK-Stil Projekt](../../core/project-sdk/msbuild-props.md) für .net Core ist viel einfacher als das Projekt Format .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e667f-154">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET Core is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="e667f-155">Abgesehen von den zuvor erwähnten `PackageReference` Einträgen müssen Sie noch nicht viel mehr tun.</span><span class="sxs-lookup"><span data-stu-id="e667f-155">Apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="e667f-156">Das neue Projekt Format [schließt standardmäßig Dateien mit bestimmten Erweiterungen](../../core/project-sdk/overview.md#default-includes-and-excludes)ein, z `.cs` . b.-Dateien und- `.xaml` Dateien, ohne dass diese explizit in die Projektdatei eingeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e667f-156">The new project format [includes files with certain extensions by default](../../core/project-sdk/overview.md#default-includes-and-excludes), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="e667f-157">Überlegungen zu Assembly.info</span><span class="sxs-lookup"><span data-stu-id="e667f-157">Assembly.info considerations</span></span>

<span data-ttu-id="e667f-158">Attribute werden für .net Core-Projekte automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="e667f-158">Attributes are autogenerated on .NET Core projects.</span></span> <span data-ttu-id="e667f-159">Wenn das Projekt eine *AssemblyInfo.cs* -Datei enthält, werden die Definitionen dupliziert, was zu Kompilierungs Konflikten führt.</span><span class="sxs-lookup"><span data-stu-id="e667f-159">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="e667f-160">Sie können die ältere *AssemblyInfo.cs* -Datei löschen oder die automatische Generierung deaktivieren, indem Sie den folgenden Eintrag der .net Core-Projektdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e667f-160">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET Core project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="e667f-161">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e667f-161">Resources</span></span>

<span data-ttu-id="e667f-162">Eingebettete Ressourcen werden automatisch eingeschlossen, aber Ressourcen sind nicht vorhanden, sodass Sie die Ressourcen in die neue Projektdatei migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="e667f-162">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="e667f-163">Paketverweise</span><span class="sxs-lookup"><span data-stu-id="e667f-163">Package references</span></span>

<span data-ttu-id="e667f-164">Mit der Option **packages.config zu packagerereferences migrieren** können Sie Ihre externen Paket Verweise problemlos in das neue Format verschieben, wie bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="e667f-164">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="e667f-165">Aktualisieren von Paketverweisen</span><span class="sxs-lookup"><span data-stu-id="e667f-165">Update package references</span></span>

<span data-ttu-id="e667f-166">Aktualisieren Sie die Versionen der Pakete, die Sie als kompatibel befunden haben, wie im vorherigen Abschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e667f-166">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="e667f-167">Korrigieren Sie den Code und den Build</span><span class="sxs-lookup"><span data-stu-id="e667f-167">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="e667f-168">Microsoft. Windows. Compatibility</span><span class="sxs-lookup"><span data-stu-id="e667f-168">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="e667f-169">Wenn Ihre Anwendung von APIs abhängig ist, die in .net Core nicht verfügbar sind, wie z. b. Registrierung, ACLs oder WCF, müssen Sie einen Verweis auf das Paket einschließen, `Microsoft.Windows.Compatibility` um diese Windows-spezifischen APIs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e667f-169">If your application depends on APIs that aren't available on .NET Core, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="e667f-170">Sie funktionieren unter .net Core, sind aber nicht enthalten, da Sie nicht plattformübergreifend sind.</span><span class="sxs-lookup"><span data-stu-id="e667f-170">They work on .NET Core but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="e667f-171">Es gibt ein Tool namens API Analyzer ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ), das Ihnen hilft, APIs zu identifizieren, die nicht mit Ihrem Code kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="e667f-171">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="e667f-172">\#If-Direktiven verwenden</span><span class="sxs-lookup"><span data-stu-id="e667f-172">Use \#if directives</span></span>

<span data-ttu-id="e667f-173">Wenn Sie unterschiedliche Ausführungs Pfade benötigen, wenn Sie auf .NET Framework und .net Core abzielen, sollten Sie Kompilierungs Konstanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e667f-173">If you need different execution paths when targeting .NET Framework and .NET Core, you should use compilation constants.</span></span> <span data-ttu-id="e667f-174">Fügen Sie \# dem Code einige if-Direktiven hinzu, um die gleiche Codebasis für beide Ziele beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="e667f-174">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net-core"></a><span data-ttu-id="e667f-175">Technologien, die in .net Core nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="e667f-175">Technologies not available on .NET Core</span></span>

<span data-ttu-id="e667f-176">Einige Technologien sind in .net Core nicht verfügbar, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="e667f-176">Some technologies aren't available on .NET Core, such as:</span></span>

* <span data-ttu-id="e667f-177">AppDomains</span><span class="sxs-lookup"><span data-stu-id="e667f-177">AppDomains</span></span>
* <span data-ttu-id="e667f-178">Remoting</span><span class="sxs-lookup"><span data-stu-id="e667f-178">Remoting</span></span>
* <span data-ttu-id="e667f-179">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="e667f-179">Code Access Security</span></span>
* <span data-ttu-id="e667f-180">WCF-Server</span><span class="sxs-lookup"><span data-stu-id="e667f-180">WCF Server</span></span>
* <span data-ttu-id="e667f-181">Windows-Workflow</span><span class="sxs-lookup"><span data-stu-id="e667f-181">Windows Workflow</span></span>

<span data-ttu-id="e667f-182">Daher müssen Sie einen Ersatz für diese Technologien finden, wenn Sie Sie in Ihrer Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e667f-182">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="e667f-183">Weitere Informationen finden Sie im Artikel [.NET Framework-Technologien, die für .net Core nicht verfügbar](../../core/porting/net-framework-tech-unavailable.md) sind.</span><span class="sxs-lookup"><span data-stu-id="e667f-183">For more information, see the [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="e667f-184">Automatisch generierte Clients neu generieren</span><span class="sxs-lookup"><span data-stu-id="e667f-184">Regenerate autogenerated clients</span></span>

<span data-ttu-id="e667f-185">Wenn Ihre Anwendung automatisch generierten Code (z. b. einen WCF-Client) verwendet, müssen Sie diesen Code ggf. erneut generieren, um .net Core als Ziel zu verwenden</span><span class="sxs-lookup"><span data-stu-id="e667f-185">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET Core.</span></span> <span data-ttu-id="e667f-186">Manchmal können Sie einige fehlende Verweise finden, da Sie möglicherweise nicht als Bestandteil des standardmäßigen Satzes von .net Core-Assemblys enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e667f-186">Sometimes, you can find some missing references since they may not be included as part of the default .NET Core assemblies set.</span></span> <span data-ttu-id="e667f-187">Mithilfe eines Tools wie <https://apisof.net/> können Sie die Assembly, in der sich der fehlende Verweis befindet, leicht finden und aus nuget hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e667f-187">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="e667f-188">Rollback von Paketversionen</span><span class="sxs-lookup"><span data-stu-id="e667f-188">Rolling back package versions</span></span>

<span data-ttu-id="e667f-189">Als allgemeine Regel haben wir bereits festgelegt, dass Sie jede einzelne Paketversion so aktualisieren, dass Sie mit .net Core kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="e667f-189">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET Core.</span></span> <span data-ttu-id="e667f-190">Allerdings können Sie feststellen, dass das Ziel einer aktualisierten und kompatiblen Version einer Assembly nicht zahlt.</span><span class="sxs-lookup"><span data-stu-id="e667f-190">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="e667f-191">Wenn die Kosten für die Änderung nicht akzeptabel sind, können Sie ein Rollback der Paketversionen in Erwägung gezogen, wobei Sie die in .NET Framework verwendeten.</span><span class="sxs-lookup"><span data-stu-id="e667f-191">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="e667f-192">Obwohl Sie möglicherweise nicht auf .net Core abzielen, sollten Sie gut funktionieren, es sei denn, Sie wenden einige nicht unterstützte APIs an.</span><span class="sxs-lookup"><span data-stu-id="e667f-192">Although they may not be targeting .NET Core, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="e667f-193">Ausführen und Testen</span><span class="sxs-lookup"><span data-stu-id="e667f-193">Run and test</span></span>

<span data-ttu-id="e667f-194">Wenn Sie die Anwendungs Erstellung ohne Fehler durchlaufen haben, können Sie den letzten Schritt der Migration starten, indem Sie jede Funktionalität testen.</span><span class="sxs-lookup"><span data-stu-id="e667f-194">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="e667f-195">In diesem letzten Schritt finden Sie verschiedene verschiedene Probleme, abhängig von der Komplexität Ihrer Anwendung und den von Ihnen verwendeten Abhängigkeiten und APIs.</span><span class="sxs-lookup"><span data-stu-id="e667f-195">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="e667f-196">Wenn Sie z. b. Konfigurationsdateien (*app.config*) verwenden, finden Sie möglicherweise einige Fehler zur Laufzeit, z. b. Konfigurations Abschnitte nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e667f-196">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="e667f-197">Wenn Sie das `Microsoft.Extensions.Configuration` nuget-Paket verwenden, sollte dieser Fehler behoben werden.</span><span class="sxs-lookup"><span data-stu-id="e667f-197">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="e667f-198">Ein weiterer Grund für Fehler ist die Verwendung der `BeginInvoke` -Methode und der- `EndInvoke` Methode, da Sie von .net Core nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e667f-198">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET Core.</span></span> <span data-ttu-id="e667f-199">Sie werden von .net Core nicht unterstützt, da Sie eine Abhängigkeit von Remoting haben, das in .net Core nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e667f-199">They aren't supported on .NET Core because they have a dependency on Remoting, which doesn't exist on .NET Core.</span></span> <span data-ttu-id="e667f-200">Um dieses Problem zu beheben, versuchen Sie, das- `await` Schlüsselwort (falls verfügbar) oder die-Methode zu verwenden <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e667f-200">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e667f-201">Mithilfe von Kompatibilitäts Analysen können Sie APIs und Code muster in Ihrem Code identifizieren, die zur Laufzeit möglicherweise Probleme mit .net Core verursachen können.</span><span class="sxs-lookup"><span data-stu-id="e667f-201">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET Core.</span></span> <span data-ttu-id="e667f-202">Wechseln Sie zu, <https://github.com/dotnet/platform-compat> und verwenden Sie den .NET API Analyzer für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="e667f-202">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="e667f-203">Migrieren einer Windows Forms Anwendung</span><span class="sxs-lookup"><span data-stu-id="e667f-203">Migrating a Windows Forms application</span></span>

<span data-ttu-id="e667f-204">Um einen kompletten Migrationsprozess einer Windows Forms Anwendung vorzustellen, haben wir uns für die Migration der in verfügbaren eShop-Beispielanwendung entschieden <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="e667f-204">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="e667f-205">Das gesamte Ergebnis der Migration finden Sie unter <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="e667f-205">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="e667f-206">Diese Anwendung zeigt einen Produktkatalog und ermöglicht dem Benutzer das Navigieren, Filtern und suchen nach Produkten.</span><span class="sxs-lookup"><span data-stu-id="e667f-206">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="e667f-207">Aus Sicht der Architektur basiert die APP auf einem externen WCF-Dienst, der als Fassade für eine Back-End-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="e667f-207">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="e667f-208">Das Hauptanwendungsfenster wird in der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e667f-208">You can see the main application window in the following picture:</span></span>

![Hauptanwendungsfenster](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="e667f-210">Wenn Sie die *csproj* -Projektdatei öffnen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e667f-210">If you open the *.csproj* project file, you can see something like this:</span></span>

![Screenshot der Inhalte der CSPROJ-Datei](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="e667f-212">Wie bereits erwähnt, hat das .net Core-Projekt einen kompakteren Stil, und Sie müssen die Projektstruktur zum neuen .net Core SDK-Stil migrieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-212">As previously mentioned, .NET Core project has a more compact style and you need to migrate the project structure to the new .NET Core SDK style.</span></span>

<span data-ttu-id="e667f-213">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt Windows Forms, und wählen Sie **Projekt**  >  **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e667f-213">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="e667f-214">Nun können Sie die CSPROJ-Datei aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-214">Now you can update the .csproj file.</span></span> <span data-ttu-id="e667f-215">Löschen Sie den gesamten Inhalt, und ersetzen Sie ihn durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e667f-215">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="e667f-216">Speichern und laden Sie das Projekt erneut.</span><span class="sxs-lookup"><span data-stu-id="e667f-216">Save and reload the project.</span></span> <span data-ttu-id="e667f-217">Nun haben Sie die Projektdatei aktualisiert, und das Projekt zielt auf .net Core ab.</span><span class="sxs-lookup"><span data-stu-id="e667f-217">You're now done updating the project file and the project is targeting the .NET Core.</span></span>

<span data-ttu-id="e667f-218">Wenn Sie das Projekt zu diesem Zeitpunkt kompilieren, finden Sie einige Fehler im Zusammenhang mit der WCF-Client Referenz.</span><span class="sxs-lookup"><span data-stu-id="e667f-218">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="e667f-219">Da dieser Code automatisch generiert wird, müssen Sie ihn neu generieren, um .net Core als Ziel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e667f-219">Since this code is autogenerated, you must regenerate it to target .NET Core.</span></span>

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="e667f-221">Löschen Sie die Datei *Reference.cs* , und generieren Sie einen neuen Dienst Client.</span><span class="sxs-lookup"><span data-stu-id="e667f-221">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="e667f-222">Klicken Sie mit der rechten Maustaste auf **verbundene Dienste** und wählen Sie die Option **verbundenen Dienst hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e667f-222">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![Screenshot des Menüs "verbundene Dienste" mit ausgewählter Option "verbundenen Dienst hinzufügen"](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="e667f-224">Das verbundene Dienste Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e667f-224">The Connected Services window opens.</span></span> <span data-ttu-id="e667f-225">Wählen Sie die Option **Microsoft WCF-Webdienst** aus.</span><span class="sxs-lookup"><span data-stu-id="e667f-225">Select the **Microsoft WCF Web Service** option.</span></span>

![Screenshot des Fensters "verbundene Dienste"](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="e667f-227">Wenn Sie den WCF-Dienst in derselben Projekt Mappe wie in diesem Beispiel verwenden, können Sie die **Ermittlungs Option auswählen** , anstatt eine Dienst-URL anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e667f-227">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![Screenshot des Fensters "WCF-Webdienst Verweis konfigurieren"](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="e667f-229">Sobald der Dienst gefunden wurde, reflektiert das Tool den API-Vertrag, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e667f-229">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="e667f-230">Ändern Sie den Namen des Namespace in, `eShopServiceReference` wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e667f-230">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![Screenshot: der API-Vertrag und der Namespace wurden geändert.](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="e667f-232">Wählen Sie die Schaltfläche **Fertig** stellen.</span><span class="sxs-lookup"><span data-stu-id="e667f-232">Select the **Finish** button.</span></span> <span data-ttu-id="e667f-233">Nach einer Weile sehen Sie den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="e667f-233">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="e667f-234">Es sollten drei automatisch generierte Dateien angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e667f-234">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="e667f-235">*Getting Started*: ein Link zu GitHub, um einige Informationen zu WCF bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e667f-235">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="e667f-236">*ConnectedService.js*: Konfigurationsparameter zum Herstellen einer Verbindung mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="e667f-236">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="e667f-237">*Reference.cs*: der tatsächliche WCF-Client Code.</span><span class="sxs-lookup"><span data-stu-id="e667f-237">*Reference.cs*: the actual WCF client code.</span></span>

![Screenshot des Fensters "Projektmappen-Explorer" mit den drei automatisch generierten Dateien](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="e667f-239">Wenn Sie die Kompilierung erneut ausführen, werden viele Fehler aus *CS* - *Dateien im* hilfsprogrammordner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e667f-239">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="e667f-240">Dieser Ordner war in der .NET Framework-Version vorhanden, jedoch nicht in der alten *csproj*-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="e667f-240">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="e667f-241">Mit dem neuen SDK-Stil-Projekt ist jedoch jede Codedatei, die unterhalb des Projektdatei Speicher Orts vorhanden ist, standardmäßig enthalten.</span><span class="sxs-lookup"><span data-stu-id="e667f-241">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="e667f-242">Das heißt, das neue .net Core-Projekt versucht, die *Dateien im hilfsprogrammordner zu* kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e667f-242">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="e667f-243">Da dieser Ordner nicht benötigt wird, können Sie ihn problemlos löschen.</span><span class="sxs-lookup"><span data-stu-id="e667f-243">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="e667f-244">Wenn Sie das Projekt erneut kompilieren und ausführen, werden die Produkt Images nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e667f-244">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="e667f-245">Das Problem ist, dass sich der Pfad zu den Dateien nun etwas geändert hat.</span><span class="sxs-lookup"><span data-stu-id="e667f-245">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="e667f-246">Um dieses Problem zu beheben, müssen Sie eine weitere Tiefe des Pfads hinzufügen und in der Datei `CatalogView.cs` die Zeile aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="e667f-246">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="e667f-247">auf</span><span class="sxs-lookup"><span data-stu-id="e667f-247">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="e667f-248">Nachdem Sie diese Änderung vorgenommen haben, können Sie überprüfen, ob die Anwendung in .net Core erwartungsgemäß gestartet und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e667f-248">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="e667f-249">Migrieren einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e667f-249">Migrating a WPF application</span></span>

<span data-ttu-id="e667f-250">Wir verwenden die `Shop.ClassicWPF` Beispielanwendung, um die Migration durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e667f-250">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="e667f-251">Die folgende Abbildung zeigt einen Screenshot der APP vor der Migration:</span><span class="sxs-lookup"><span data-stu-id="e667f-251">The following image shows a screenshot of the app before migration:</span></span>

![Beispiel-APP vor der Migration](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="e667f-253">Diese Anwendung verwendet eine lokale SQL Server Express Datenbank, um die Produktkatalog Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e667f-253">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="e667f-254">Der Zugriff auf diese Datenbank erfolgt direkt über die WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e667f-254">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="e667f-255">Zunächst müssen Sie die *csproj* -Datei auf den neuen SDK-Stil aktualisieren, der von .net Core-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e667f-255">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="e667f-256">Befolgen Sie dieselben Schritte, die in der Windows Forms Migration beschrieben werden: Sie entladen das Projekt, öffnen die *csproj* -Datei, aktualisieren den Inhalt und laden das Projekt erneut.</span><span class="sxs-lookup"><span data-stu-id="e667f-256">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="e667f-257">Löschen Sie in diesem Fall den gesamten Inhalt der *csproj* -Datei, und ersetzen Sie ihn durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e667f-257">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWpf>true</UseWpf>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="e667f-258">Wenn Sie das Projekt erneut laden und kompilieren, erhalten Sie die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="e667f-258">If you reload the project and compile it, you'll get the following error:</span></span>

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="e667f-260">Da Sie alle *csproj* -Inhalte gelöscht haben, haben Sie eine Projekt Verweis Spezifikation verloren, die im alten Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e667f-260">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="e667f-261">Sie müssen diese Zeile lediglich der *csproj* -Datei hinzufügen, um den Projekt Verweis einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="e667f-261">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="e667f-262">Sie können Visual Studio auch helfen, indem Sie mit der rechten Maustaste auf den Knoten **Abhängigkeiten** klicken und **Projekt Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e667f-262">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="e667f-263">Wählen Sie das Projekt aus der Projekt Mappe, und klicken Sie auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="e667f-263">Select the project from the solution and click **OK**:</span></span>

![Screenshot des Dialog Felds "Verweis-Manager" mit ausgewähltem "eShop. SqlProvider"-Projekt](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="e667f-265">Nachdem Sie den fehlenden Projekt Verweis hinzugefügt haben, wird die Anwendung in .net Core wie erwartet kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e667f-265">Once you add the missing project reference, the application compiles and runs as expected on .NET Core.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e667f-266">[Zurück](windows-migration.md)
>[Weiter](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e667f-266">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>
