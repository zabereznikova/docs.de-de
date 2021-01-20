---
title: Beispiel für die Migration zu .net 5
description: Es wird gezeigt, wie Sie eine Beispielanwendung migrieren, die .NET Framework auf .net 5 abzielt.
ms.date: 01/19/2021
ms.openlocfilehash: f924f90046fdcd7dfe5e23740fc921a09383a81a
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98618030"
---
# <a name="example-of-migrating-to-net"></a><span data-ttu-id="06898-103">Beispiel für die Migration zu .net</span><span class="sxs-lookup"><span data-stu-id="06898-103">Example of migrating to .NET</span></span>

<span data-ttu-id="06898-104">In diesem Kapitel werden praktische Richtlinien vorgestellt, die Ihnen bei der Migration Ihrer vorhandenen Anwendung von .NET Framework zu .net helfen.</span><span class="sxs-lookup"><span data-stu-id="06898-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET.</span></span>

<span data-ttu-id="06898-105">Wir präsentieren einen gut strukturierten Prozess, den Sie befolgen können, und die wichtigsten Punkte, die bei jedem Schritt berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="06898-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="06898-106">Anschließend wird ein schrittweises Migrationsverfahren für eine Beispiel-Desktop Anwendung, beides aus WinForms-und WPF-Versionen, dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="06898-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="06898-107">Übersicht über den Migrationsprozess</span><span class="sxs-lookup"><span data-stu-id="06898-107">Migration process overview</span></span>

<span data-ttu-id="06898-108">Der Migrations Vorgang besteht aus vier aufeinander folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="06898-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="06898-109">**Vorbereitung**: verstehen Sie die Abhängigkeiten des Projekts, um eine Vorstellung davon zu erhalten, was vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="06898-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="06898-110">In diesem Schritt nehmen Sie das aktuelle Projekt in einen Zustand, der den Startpunkt für die Migration vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="06898-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="06898-111">**Projektdatei migrieren:** .net-Projekte verwenden das neue Projekt Format im SDK-Stil.</span><span class="sxs-lookup"><span data-stu-id="06898-111">**Migrate Project File:** .NET projects use the new SDK-style project format.</span></span> <span data-ttu-id="06898-112">Erstellen Sie eine neue Projektdatei mit diesem Format, oder aktualisieren Sie die Datei, für die Sie den SDK-Stil verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="06898-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="06898-113">**Korrigieren Sie den Code und den Build:** Erstellen Sie den Code in .net, der die Unterschiede auf API-Ebene zwischen .NET Framework und .net adressiert.</span><span class="sxs-lookup"><span data-stu-id="06898-113">**Fix code and build:** Build the code in .NET addressing API-level differences between .NET Framework and .NET.</span></span> <span data-ttu-id="06898-114">Aktualisieren Sie bei Bedarf Pakete von Drittanbietern auf diejenigen, die .NET unterstützen.</span><span class="sxs-lookup"><span data-stu-id="06898-114">If needed, update third-party packages to the ones that support .NET.</span></span>

4. <span data-ttu-id="06898-115">**Ausführen und testen:** Möglicherweise gibt es Unterschiede, die bis zur Laufzeit nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="06898-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="06898-116">Vergessen Sie daher nicht, die Anwendung auszuführen und zu testen, ob alles erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="06898-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="06898-117">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="06898-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="06898-118">Migrieren packages.config Datei</span><span class="sxs-lookup"><span data-stu-id="06898-118">Migrate packages.config file</span></span>

<span data-ttu-id="06898-119">In einer .NET Framework Anwendung werden alle Verweise auf externe Pakete in der *packages.config* -Datei deklariert.</span><span class="sxs-lookup"><span data-stu-id="06898-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="06898-120">In .net ist es nicht mehr erforderlich, die *packages.config* -Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="06898-120">In .NET, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="06898-121">Verwenden Sie stattdessen die [packagereferenzierungseigenschaft](../../core/project-sdk/msbuild-props.md#packagereference) in der Projektdatei, um die nuget-Pakete für Ihre APP anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06898-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="06898-122">Daher müssen Sie von einem Format in ein anderes wechseln.</span><span class="sxs-lookup"><span data-stu-id="06898-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="06898-123">Sie können das Update manuell ausführen, indem Sie die in der *packages.config* -Datei enthaltenen Abhängigkeiten übernehmen und Sie in die Projektdatei mit dem `PackageReference` Format migrieren.</span><span class="sxs-lookup"><span data-stu-id="06898-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="06898-124">Alternativ können Sie Visual Studio für Sie ausführen lassen: Klicken Sie mit der rechten Maustaste auf die Datei *packages.config* , und wählen Sie die Option **packages.config zu packagereferenzierung migrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="06898-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net"></a><span data-ttu-id="06898-125">Überprüfen aller Abhängigkeits Kompatibilität in .net</span><span class="sxs-lookup"><span data-stu-id="06898-125">Verify every dependency compatibility in .NET</span></span>

<span data-ttu-id="06898-126">Nachdem Sie die Paket Verweise migriert haben, müssen Sie jeden Verweis auf Kompatibilität überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06898-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="06898-127">Sie können die Abhängigkeiten der einzelnen nuget-Pakete untersuchen, die Ihre Anwendung auf [nuget.org](https://www.nuget.org/)verwendet. Wenn das Paket .NET Standard Abhängigkeiten aufweist, wird es auf .net 5,0 funktionieren, da .net alle Versionen von .NET Standard [unterstützt](../../standard/net-standard.md#net-implementation-support) .</span><span class="sxs-lookup"><span data-stu-id="06898-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET 5.0 because .NET [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="06898-128">Die folgende Abbildung zeigt die Abhängigkeiten für das `Castle.Windsor` Paket:</span><span class="sxs-lookup"><span data-stu-id="06898-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Screenshot der nuget-Abhängigkeiten für das Castle. Windsor-Paket](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="06898-130">Zum Überprüfen der Paket Kompatibilität können Sie das Tool verwenden <https://fuget.org> , das ausführlichere Informationen zu Versionen und Abhängigkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="06898-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="06898-131">Möglicherweise verweist das Projekt auf ältere Paketversionen, die .net nicht unterstützen, aber Sie finden neuere Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="06898-131">Maybe the project is referencing older package versions that don't support .NET, but you might find newer versions that do support it.</span></span> <span data-ttu-id="06898-132">Das Aktualisieren von Paketen auf neuere Versionen ist im Allgemeinen eine gute Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="06898-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="06898-133">Sie sollten jedoch berücksichtigen, dass durch die Aktualisierung der Paketversion einige wichtige Änderungen eingeführt werden, die das Aktualisieren Ihres Codes erzwingen würden.</span><span class="sxs-lookup"><span data-stu-id="06898-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="06898-134">Was geschieht, wenn Sie keine kompatible Version finden?</span><span class="sxs-lookup"><span data-stu-id="06898-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="06898-135">Was geschieht, wenn Sie die Version eines Pakets aufgrund dieser wichtigen Änderungen nicht aktualisieren möchten?</span><span class="sxs-lookup"><span data-stu-id="06898-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="06898-136">Keine Sorge, da es möglich ist, von einer .NET-Anwendung aus .NET Framework Paketen zu abhängen.</span><span class="sxs-lookup"><span data-stu-id="06898-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET application.</span></span> <span data-ttu-id="06898-137">Vergessen Sie nicht, Sie ausgiebig zu testen, da Sie Laufzeitfehler verursachen kann, wenn das externe Paket eine API aufruft, die in .net nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="06898-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET.</span></span> <span data-ttu-id="06898-138">Dies eignet sich hervorragend für den Fall, dass Sie ein altes Paket verwenden, das nicht aktualisiert wird, und Sie können einfach neu zuweisen, um mit .net zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="06898-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="06898-139">Auf API-Kompatibilität überprüfen</span><span class="sxs-lookup"><span data-stu-id="06898-139">Check for API compatibility</span></span>

<span data-ttu-id="06898-140">Da die API-Oberfläche in .NET Framework und .net ähnlich, aber nicht identisch ist, müssen Sie überprüfen, welche APIs in .net verfügbar sind und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="06898-140">Since the API surface in .NET Framework and .NET is similar but not identical, you must check which APIs are available on .NET and which aren't.</span></span> <span data-ttu-id="06898-141">Sie können das Tool .net-Portabilitäts Analyse verwenden, um APIs zu verwenden, die nicht in .net vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="06898-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET.</span></span> <span data-ttu-id="06898-142">Sie untersucht die binäre Ebene der APP, extrahiert alle APIs, die aufgerufen werden, und listet dann auf, welche APIs in Ihrem Ziel Framework nicht verfügbar sind (in diesem Fall .net 5,0).</span><span class="sxs-lookup"><span data-stu-id="06898-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET 5.0 in this case).</span></span>

<span data-ttu-id="06898-143">Weitere Informationen zu diesem Tool finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="06898-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="06898-144">Ein interessanter Aspekt dieses Tools besteht darin, dass nur die Unterschiede von Ihrem eigenen Code und nicht von Code aus externen Paketen, die Sie nicht ändern können, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="06898-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="06898-145">Denken Sie daran, dass Sie die meisten dieser Pakete aktualisiert haben müssen, damit Sie mit .net funktionieren.</span><span class="sxs-lookup"><span data-stu-id="06898-145">Remember you should have updated most of these packages to make them work with .NET.</span></span>

### <a name="migrate-with-try-convert-tool"></a><span data-ttu-id="06898-146">Migrieren mit Tool zum Konvertieren von versuchen</span><span class="sxs-lookup"><span data-stu-id="06898-146">Migrate with Try Convert tool</span></span>

<span data-ttu-id="06898-147">Das [try Convert](https://github.com/dotnet/try-convert/releases) -Tool eignet sich hervorragend zum Migrieren eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="06898-147">The [Try Convert](https://github.com/dotnet/try-convert/releases) tool is a great way to migrate a project.</span></span> <span data-ttu-id="06898-148">Dabei handelt es sich um ein globales Tool, das versucht, die Projektdatei vom alten Stil auf den neuen SDK-Stil zu aktualisieren und die anwendbaren Projekte auf .net 5 umzustellen.</span><span class="sxs-lookup"><span data-stu-id="06898-148">It's a global tool that attempts to upgrade your project file from the old style to the new SDK style, and retargets applicable projects to .NET 5.</span></span> <span data-ttu-id="06898-149">Nach der Installation können Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="06898-149">Once installed, you can run the following commands:</span></span>

```dotnetcli
try-convert -p "<path to your project file>"
```

<span data-ttu-id="06898-150">Oder:</span><span class="sxs-lookup"><span data-stu-id="06898-150">Or:</span></span>

```dotnetcli
try-convert -w "<path to your solution>"
```

<span data-ttu-id="06898-151">Nachdem das Tool versucht hat, die Konvertierung auszuführen, laden Sie Ihre Dateien in Visual Studio neu, um Sie auszuführen und zu testen</span><span class="sxs-lookup"><span data-stu-id="06898-151">After the tool attempts the conversion, reload your files in Visual Studio to run and test.</span></span> <span data-ttu-id="06898-152">Die Konvertierung kann nicht durchgeführt werden, weil die Konvertierung aufgrund der Besonderheiten ihres Projekts nicht durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06898-152">There's a possibility that Try Convert won't be able to perform the conversion due to the specifics of your project.</span></span> <span data-ttu-id="06898-153">In diesem Fall können Sie die folgenden Schritte durchführen.</span><span class="sxs-lookup"><span data-stu-id="06898-153">In that case, you can refer the below steps.</span></span>

#### <a name="migrate-manually"></a><span data-ttu-id="06898-154">Manuelles Migrieren</span><span class="sxs-lookup"><span data-stu-id="06898-154">Migrate manually</span></span>

1. <span data-ttu-id="06898-155">Erstellen des neuen .NET-Projekts</span><span class="sxs-lookup"><span data-stu-id="06898-155">Create the new .NET project</span></span>

<span data-ttu-id="06898-156">In den meisten Fällen möchten Sie Ihr vorhandenes Projekt auf das neue .NET-Format aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="06898-156">In most cases, you'll want to update your existing project to the new .NET format.</span></span> <span data-ttu-id="06898-157">Sie können jedoch auch ein neues Projekt erstellen, während Sie das alte Projekt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="06898-157">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="06898-158">Der Hauptnachteil beim Aktualisieren des alten Projekts besteht darin, dass Sie die Designer Unterstützung verlieren, was für Sie und Ihr Entwicklungsteam wichtig sein kann.</span><span class="sxs-lookup"><span data-stu-id="06898-158">The main drawback from updating the old project is that you lose designer support, which may be important to you and your development team.</span></span> <span data-ttu-id="06898-159">Wenn Sie den Designer weiterhin verwenden möchten, müssen Sie ein neues .net-Projekt parallel zum alten erstellen und Assets freigeben.</span><span class="sxs-lookup"><span data-stu-id="06898-159">If you want to keep using the designer, you must create a new .NET project in parallel with the old one and share assets.</span></span> <span data-ttu-id="06898-160">Wenn Sie Benutzeroberflächen Elemente im Designer ändern müssen, können Sie dazu zum alten Projekt wechseln.</span><span class="sxs-lookup"><span data-stu-id="06898-160">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="06898-161">Und da Assets verknüpft sind, werden Sie ebenfalls im .net-Projekt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="06898-161">And since assets are linked, they'll be updated in the .NET project as well.</span></span>

<span data-ttu-id="06898-162">Das [SDK-Stil Projekt](../../core/project-sdk/msbuild-props.md) für .net ist viel einfacher als das Projekt Format .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="06898-162">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="06898-163">Abgesehen von den zuvor erwähnten `PackageReference` Einträgen müssen Sie noch nicht viel mehr tun.</span><span class="sxs-lookup"><span data-stu-id="06898-163">Apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="06898-164">Das neue Projekt Format [schließt standardmäßig Dateien mit bestimmten Erweiterungen](../../core/project-sdk/overview.md#default-includes-and-excludes)ein, z `.cs` . b.-Dateien und- `.xaml` Dateien, ohne dass diese explizit in die Projektdatei eingeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="06898-164">The new project format [includes files with certain extensions by default](../../core/project-sdk/overview.md#default-includes-and-excludes), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="06898-165">AssemblyInfo-Überlegungen</span><span class="sxs-lookup"><span data-stu-id="06898-165">AssemblyInfo considerations</span></span>

<span data-ttu-id="06898-166">Attribute werden für .net-Projekte automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="06898-166">Attributes are autogenerated on .NET projects.</span></span> <span data-ttu-id="06898-167">Wenn das Projekt eine *AssemblyInfo.cs* -Datei enthält, werden die Definitionen dupliziert, was zu Kompilierungs Konflikten führt.</span><span class="sxs-lookup"><span data-stu-id="06898-167">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="06898-168">Sie können die ältere *AssemblyInfo.cs* -Datei löschen oder die automatische Generierung deaktivieren, indem Sie den folgenden Eintrag zur .net-Projektdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="06898-168">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>    
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="06898-169">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="06898-169">Resources</span></span>

<span data-ttu-id="06898-170">Eingebettete Ressourcen werden automatisch eingeschlossen, aber Ressourcen sind nicht vorhanden, sodass Sie die Ressourcen in die neue Projektdatei migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="06898-170">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="06898-171">Paketverweise</span><span class="sxs-lookup"><span data-stu-id="06898-171">Package references</span></span>

<span data-ttu-id="06898-172">Mit der Option **packages.config zu packagerereferences migrieren** können Sie Ihre externen Paket Verweise problemlos in das neue Format verschieben, wie bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="06898-172">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="06898-173">Aktualisieren von Paketverweisen</span><span class="sxs-lookup"><span data-stu-id="06898-173">Update package references</span></span>

<span data-ttu-id="06898-174">Aktualisieren Sie die Versionen der Pakete, die Sie als kompatibel befunden haben, wie im vorherigen Abschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="06898-174">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="06898-175">Korrigieren Sie den Code und den Build</span><span class="sxs-lookup"><span data-stu-id="06898-175">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="06898-176">Microsoft. Windows. Compatibility</span><span class="sxs-lookup"><span data-stu-id="06898-176">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="06898-177">Wenn Ihre Anwendung von APIs abhängig ist, die in .net nicht verfügbar sind, z. b. Registrierung, ACLs oder WCF, müssen Sie einen Verweis auf das Paket einschließen, `Microsoft.Windows.Compatibility` um diese Windows-spezifischen APIs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="06898-177">If your application depends on APIs that aren't available on .NET, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="06898-178">Sie funktionieren mit .net, sind jedoch nicht enthalten, da Sie nicht plattformübergreifend sind.</span><span class="sxs-lookup"><span data-stu-id="06898-178">They work on .NET but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="06898-179">Es gibt ein Tool namens API Analyzer ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ), das Ihnen hilft, APIs zu identifizieren, die nicht mit Ihrem Code kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="06898-179">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="06898-180">\#If-Direktiven verwenden</span><span class="sxs-lookup"><span data-stu-id="06898-180">Use \#if directives</span></span>

<span data-ttu-id="06898-181">Wenn Sie unterschiedliche Ausführungs Pfade benötigen, wenn Sie auf .NET Framework und .net abzielen, sollten Sie Kompilierungs Konstanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="06898-181">If you need different execution paths when targeting .NET Framework and .NET, you should use compilation constants.</span></span> <span data-ttu-id="06898-182">Fügen Sie \# dem Code einige if-Direktiven hinzu, um die gleiche Codebasis für beide Ziele beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="06898-182">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net"></a><span data-ttu-id="06898-183">Technologien, die in .net nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="06898-183">Technologies not available on .NET</span></span>

<span data-ttu-id="06898-184">Einige Technologien sind in .net nicht verfügbar, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="06898-184">Some technologies aren't available on .NET, such as:</span></span>

* <span data-ttu-id="06898-185">AppDomains</span><span class="sxs-lookup"><span data-stu-id="06898-185">AppDomains</span></span>
* <span data-ttu-id="06898-186">Remoting</span><span class="sxs-lookup"><span data-stu-id="06898-186">Remoting</span></span>
* <span data-ttu-id="06898-187">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="06898-187">Code Access Security</span></span>
* <span data-ttu-id="06898-188">WCF-Server</span><span class="sxs-lookup"><span data-stu-id="06898-188">WCF Server</span></span>
* <span data-ttu-id="06898-189">Windows-Workflow</span><span class="sxs-lookup"><span data-stu-id="06898-189">Windows Workflow</span></span>

<span data-ttu-id="06898-190">Daher müssen Sie einen Ersatz für diese Technologien finden, wenn Sie Sie in Ihrer Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="06898-190">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="06898-191">Weitere Informationen finden Sie im Artikel [.NET Framework Technologien, die auf .net Core und .net 5 + nicht verfügbar](../../core/porting/net-framework-tech-unavailable.md) sind.</span><span class="sxs-lookup"><span data-stu-id="06898-191">For more information, see the [.NET Framework technologies unavailable on .NET Core and .NET 5+](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="06898-192">Automatisch generierte Clients neu generieren</span><span class="sxs-lookup"><span data-stu-id="06898-192">Regenerate autogenerated clients</span></span>

<span data-ttu-id="06898-193">Wenn die Anwendung automatisch generierten Code (z. b. einen WCF-Client) verwendet, müssen Sie diesen Code möglicherweise erneut generieren, um .net als Ziel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="06898-193">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET.</span></span> <span data-ttu-id="06898-194">Manchmal können Sie einige fehlende Verweise finden, da Sie möglicherweise nicht als Bestandteil des standardmäßigen .net-Assemblysatzes enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="06898-194">Sometimes, you can find some missing references since they may not be included as part of the default .NET assemblies set.</span></span> <span data-ttu-id="06898-195">Mithilfe eines Tools wie <https://apisof.net/> können Sie die Assembly, in der sich der fehlende Verweis befindet, leicht finden und aus nuget hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06898-195">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="06898-196">Rollback von Paketversionen</span><span class="sxs-lookup"><span data-stu-id="06898-196">Rolling back package versions</span></span>

<span data-ttu-id="06898-197">Als allgemeine Regel haben wir bereits festgelegt, dass Sie jede einzelne Paketversion so aktualisieren, dass Sie mit .NET kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="06898-197">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET.</span></span> <span data-ttu-id="06898-198">Allerdings können Sie feststellen, dass das Ziel einer aktualisierten und kompatiblen Version einer Assembly nicht zahlt.</span><span class="sxs-lookup"><span data-stu-id="06898-198">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="06898-199">Wenn die Kosten für die Änderung nicht akzeptabel sind, können Sie ein Rollback der Paketversionen in Erwägung gezogen, wobei Sie die in .NET Framework verwendeten.</span><span class="sxs-lookup"><span data-stu-id="06898-199">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="06898-200">Obwohl Sie möglicherweise nicht auf .net abzielen, sollten Sie gut funktionieren, es sei denn, Sie nennen einige nicht unterstützte APIs.</span><span class="sxs-lookup"><span data-stu-id="06898-200">Although they may not be targeting .NET, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="06898-201">Ausführen und Testen</span><span class="sxs-lookup"><span data-stu-id="06898-201">Run and test</span></span>

<span data-ttu-id="06898-202">Wenn Sie die Anwendungs Erstellung ohne Fehler durchlaufen haben, können Sie den letzten Schritt der Migration starten, indem Sie jede Funktionalität testen.</span><span class="sxs-lookup"><span data-stu-id="06898-202">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="06898-203">In diesem letzten Schritt finden Sie verschiedene verschiedene Probleme, abhängig von der Komplexität Ihrer Anwendung und den von Ihnen verwendeten Abhängigkeiten und APIs.</span><span class="sxs-lookup"><span data-stu-id="06898-203">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="06898-204">Wenn Sie z. b. Konfigurationsdateien (*app.config*) verwenden, finden Sie möglicherweise einige Fehler zur Laufzeit, z. b. Konfigurations Abschnitte nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="06898-204">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="06898-205">Wenn Sie das `Microsoft.Extensions.Configuration` nuget-Paket verwenden, sollte dieser Fehler behoben werden.</span><span class="sxs-lookup"><span data-stu-id="06898-205">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="06898-206">Ein weiterer Grund für Fehler ist die Verwendung der `BeginInvoke` -Methode und der- `EndInvoke` Methode, da Sie unter .net nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="06898-206">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET.</span></span> <span data-ttu-id="06898-207">Sie werden von .net nicht unterstützt, da Sie eine Abhängigkeit von Remoting aufweisen, das in .net nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="06898-207">They aren't supported on .NET because they have a dependency on Remoting, which doesn't exist on .NET.</span></span> <span data-ttu-id="06898-208">Um dieses Problem zu beheben, versuchen Sie, das- `await` Schlüsselwort (falls verfügbar) oder die-Methode zu verwenden <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="06898-208">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="06898-209">Mithilfe von Kompatibilitäts Analysen können Sie APIs und Code muster in Ihrem Code identifizieren, die zur Laufzeit möglicherweise Probleme mit .net verursachen können.</span><span class="sxs-lookup"><span data-stu-id="06898-209">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET.</span></span> <span data-ttu-id="06898-210">Wechseln Sie zu, <https://github.com/dotnet/platform-compat> und verwenden Sie den .NET API Analyzer für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="06898-210">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="06898-211">Migrieren einer Windows Forms Anwendung</span><span class="sxs-lookup"><span data-stu-id="06898-211">Migrating a Windows Forms application</span></span>

<span data-ttu-id="06898-212">Um einen kompletten Migrationsprozess einer Windows Forms Anwendung vorzustellen, haben wir uns für die Migration der in verfügbaren eShop-Beispielanwendung entschieden <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="06898-212">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="06898-213">Das gesamte Ergebnis der Migration finden Sie unter <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="06898-213">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="06898-214">Diese Anwendung zeigt einen Produktkatalog und ermöglicht dem Benutzer das Navigieren, Filtern und suchen nach Produkten.</span><span class="sxs-lookup"><span data-stu-id="06898-214">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="06898-215">Aus Sicht der Architektur basiert die APP auf einem externen WCF-Dienst, der als Fassade für eine Back-End-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="06898-215">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="06898-216">Das Hauptanwendungsfenster wird in der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="06898-216">You can see the main application window in the following picture:</span></span>

![Hauptanwendungsfenster](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="06898-218">Wenn Sie die *csproj* -Projektdatei öffnen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="06898-218">If you open the *.csproj* project file, you can see something like this:</span></span>

![Screenshot der Inhalte der CSPROJ-Datei](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="06898-220">Wie bereits erwähnt, hat das .net-Projekt einen kompakteren Stil, und Sie müssen die Projektstruktur zum neuen .NET SDK-Stil migrieren.</span><span class="sxs-lookup"><span data-stu-id="06898-220">As previously mentioned, .NET project has a more compact style and you need to migrate the project structure to the new .NET SDK style.</span></span>

<span data-ttu-id="06898-221">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt Windows Forms, und wählen Sie **Projekt**  >  **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="06898-221">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="06898-222">Nun können Sie die CSPROJ-Datei aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="06898-222">Now you can update the .csproj file.</span></span> <span data-ttu-id="06898-223">Löschen Sie den gesamten Inhalt, und ersetzen Sie ihn durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="06898-223">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="06898-224">Speichern und laden Sie das Projekt erneut.</span><span class="sxs-lookup"><span data-stu-id="06898-224">Save and reload the project.</span></span> <span data-ttu-id="06898-225">Nun haben Sie die Projektdatei aktualisiert, und das Projekt ist auf .net ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="06898-225">You're now done updating the project file and the project is targeting the .NET.</span></span>

<span data-ttu-id="06898-226">Wenn Sie das Projekt zu diesem Zeitpunkt kompilieren, finden Sie einige Fehler im Zusammenhang mit der WCF-Client Referenz.</span><span class="sxs-lookup"><span data-stu-id="06898-226">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="06898-227">Da dieser Code automatisch generiert wird, müssen Sie ihn für das Ziel .net neu generieren.</span><span class="sxs-lookup"><span data-stu-id="06898-227">Since this code is autogenerated, you must regenerate it to target .NET.</span></span>

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="06898-229">Löschen Sie die Datei *Reference.cs* , und generieren Sie einen neuen Dienst Client.</span><span class="sxs-lookup"><span data-stu-id="06898-229">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="06898-230">Klicken Sie mit der rechten Maustaste auf **verbundene Dienste** und wählen Sie die Option **verbundenen Dienst hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="06898-230">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![Screenshot des Menüs "verbundene Dienste" mit ausgewählter Option "verbundenen Dienst hinzufügen"](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="06898-232">Das verbundene Dienste Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="06898-232">The Connected Services window opens.</span></span> <span data-ttu-id="06898-233">Wählen Sie die Option **Microsoft WCF-Webdienst** aus.</span><span class="sxs-lookup"><span data-stu-id="06898-233">Select the **Microsoft WCF Web Service** option.</span></span>

![Screenshot des Fensters "verbundene Dienste"](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="06898-235">Wenn Sie den WCF-Dienst in derselben Projekt Mappe wie in diesem Beispiel verwenden, können Sie die **Ermittlungs Option auswählen** , anstatt eine Dienst-URL anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06898-235">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![Screenshot des Fensters "WCF-Webdienst Verweis konfigurieren"](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="06898-237">Sobald der Dienst gefunden wurde, reflektiert das Tool den API-Vertrag, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="06898-237">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="06898-238">Ändern Sie den Namen des Namespace in, `eShopServiceReference` wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="06898-238">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![Screenshot: der API-Vertrag und der Namespace wurden geändert.](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="06898-240">Wählen Sie die Schaltfläche **Fertig** stellen.</span><span class="sxs-lookup"><span data-stu-id="06898-240">Select the **Finish** button.</span></span> <span data-ttu-id="06898-241">Nach einer Weile sehen Sie den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="06898-241">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="06898-242">Es sollten drei automatisch generierte Dateien angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="06898-242">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="06898-243">*Getting Started*: ein Link zu GitHub, um einige Informationen zu WCF bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="06898-243">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="06898-244">*ConnectedService.js*: Konfigurationsparameter zum Herstellen einer Verbindung mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="06898-244">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="06898-245">*Reference.cs*: der tatsächliche WCF-Client Code.</span><span class="sxs-lookup"><span data-stu-id="06898-245">*Reference.cs*: the actual WCF client code.</span></span>

![Screenshot des Fensters "Projektmappen-Explorer" mit den drei automatisch generierten Dateien](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="06898-247">Wenn Sie die Kompilierung erneut ausführen, werden viele Fehler aus *CS* - *Dateien im* hilfsprogrammordner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06898-247">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="06898-248">Dieser Ordner war in der .NET Framework-Version vorhanden, jedoch nicht in der alten *csproj*-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="06898-248">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="06898-249">Mit dem neuen SDK-Stil-Projekt ist jedoch jede Codedatei, die unterhalb des Projektdatei Speicher Orts vorhanden ist, standardmäßig enthalten.</span><span class="sxs-lookup"><span data-stu-id="06898-249">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="06898-250">Das heißt, das neue .net Core-Projekt versucht, die *Dateien im hilfsprogrammordner zu* kompilieren.</span><span class="sxs-lookup"><span data-stu-id="06898-250">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="06898-251">Da dieser Ordner nicht benötigt wird, können Sie ihn problemlos löschen.</span><span class="sxs-lookup"><span data-stu-id="06898-251">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="06898-252">Wenn Sie das Projekt erneut kompilieren und ausführen, werden die Produkt Images nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06898-252">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="06898-253">Das Problem ist, dass sich der Pfad zu den Dateien nun etwas geändert hat.</span><span class="sxs-lookup"><span data-stu-id="06898-253">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="06898-254">Um dieses Problem zu beheben, müssen Sie eine weitere Tiefe des Pfads hinzufügen und in der Datei `CatalogView.cs` die Zeile aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="06898-254">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="06898-255">auf</span><span class="sxs-lookup"><span data-stu-id="06898-255">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="06898-256">Nachdem Sie diese Änderung vorgenommen haben, können Sie überprüfen, ob die Anwendung in .net Core erwartungsgemäß gestartet und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06898-256">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="06898-257">Migrieren einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="06898-257">Migrating a WPF application</span></span>

<span data-ttu-id="06898-258">Wir verwenden die `Shop.ClassicWPF` Beispielanwendung, um die Migration durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="06898-258">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="06898-259">Die folgende Abbildung zeigt einen Screenshot der APP vor der Migration:</span><span class="sxs-lookup"><span data-stu-id="06898-259">The following image shows a screenshot of the app before migration:</span></span>

![Beispiel-APP vor der Migration](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="06898-261">Diese Anwendung verwendet eine lokale SQL Server Express Datenbank, um die Produktkatalog Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="06898-261">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="06898-262">Der Zugriff auf diese Datenbank erfolgt direkt über die WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="06898-262">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="06898-263">Zunächst müssen Sie die *csproj* -Datei auf den neuen SDK-Stil aktualisieren, der von .net Core-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06898-263">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="06898-264">Befolgen Sie dieselben Schritte, die in der Windows Forms Migration beschrieben werden: Sie entladen das Projekt, öffnen die *csproj* -Datei, aktualisieren den Inhalt und laden das Projekt erneut.</span><span class="sxs-lookup"><span data-stu-id="06898-264">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="06898-265">Löschen Sie in diesem Fall den gesamten Inhalt der *csproj* -Datei, und ersetzen Sie ihn durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="06898-265">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
 <Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWpf>true</UseWpf>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="06898-266">Wenn Sie das Projekt erneut laden und kompilieren, erhalten Sie die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="06898-266">If you reload the project and compile it, you'll get the following error:</span></span>

![Screenshot der Kompilierungsfehler in Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="06898-268">Da Sie alle *csproj* -Inhalte gelöscht haben, haben Sie eine Projekt Verweis Spezifikation verloren, die im alten Projekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="06898-268">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="06898-269">Sie müssen diese Zeile lediglich der *csproj* -Datei hinzufügen, um den Projekt Verweis einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="06898-269">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="06898-270">Sie können Visual Studio auch helfen, indem Sie mit der rechten Maustaste auf den Knoten **Abhängigkeiten** klicken und **Projekt Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="06898-270">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="06898-271">Wählen Sie das Projekt aus der Projekt Mappe, und klicken Sie auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="06898-271">Select the project from the solution and click **OK**:</span></span>

![Screenshot des Dialog Felds "Verweis-Manager" mit ausgewähltem "eShop. SqlProvider"-Projekt](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="06898-273">Nachdem Sie den fehlenden Projekt Verweis hinzugefügt haben, wird die Anwendung in .net wie erwartet kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06898-273">Once you add the missing project reference, the application compiles and runs as expected on .NET.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06898-274">[Zurück](windows-migration.md)
>[Weiter](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="06898-274">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>
