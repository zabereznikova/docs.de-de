---
title: Abhängigkeiten und .NET-Bibliotheken
description: Hier finden Sie Empfehlungen zu Best Practices für die Verwaltung von NuGet-Abhängigkeiten in .NET-Bibliotheken.
ms.date: 10/02/2018
ms.openlocfilehash: 6a260b54c45a0cd231059ab3bc6f2707ef7fb20e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731481"
---
# <a name="dependencies"></a><span data-ttu-id="9f500-103">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="9f500-103">Dependencies</span></span>

<span data-ttu-id="9f500-104">Die einfachste Methode zum Hinzufügen von Abhängigkeiten zu einer .NET-Bibliothek sind NuGet-Paketverweise.</span><span class="sxs-lookup"><span data-stu-id="9f500-104">The primary way of adding dependencies to a .NET library is referencing NuGet packages.</span></span> <span data-ttu-id="9f500-105">Mit NuGet-Paketverweisen können Sie bereits geschriebene Funktionen schnell wiederverwenden. Allerdings sind sie für .NET-Entwickler auch eine häufige Ursache von Problemen.</span><span class="sxs-lookup"><span data-stu-id="9f500-105">NuGet package references allow you to quickly reuse and leverage already written functionality, but they're a common source of friction for .NET developers.</span></span> <span data-ttu-id="9f500-106">Die ordnungsgemäße Verwaltung von Abhängigkeiten ist wichtig, um zu verhindern, dass Änderungen in anderen .NET-Bibliotheken zu Problemen in Ihrer .NET-Bibliothek und umgekehrt führen.</span><span class="sxs-lookup"><span data-stu-id="9f500-106">Correctly managing dependencies is important to prevent changes in other .NET libraries from breaking your .NET library, and vice versa!</span></span>

## <a name="diamond-dependencies"></a><span data-ttu-id="9f500-107">Rautenabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="9f500-107">Diamond dependencies</span></span>

<span data-ttu-id="9f500-108">Bei einem .NET-Projekt sind sehr häufig mehrere Versionen eines Pakets in der Abhängigkeitsstruktur vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9f500-108">It's a common situation for a .NET project to have multiple versions of a package in its dependency tree.</span></span> <span data-ttu-id="9f500-109">Eine App kann beispielsweise von zwei NuGet-Paketen abhängig sein, von denen jedes wiederum von verschiedenen Versionen desselben Pakets abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="9f500-109">For example, an app depends on two NuGet packages, each of which depends on different versions of the same package.</span></span> <span data-ttu-id="9f500-110">Dadurch entsteht eine Rautenabhängigkeit im Abhängigkeitsdiagramm der App.</span><span class="sxs-lookup"><span data-stu-id="9f500-110">A diamond dependency now exists in the app's dependency graph.</span></span>

<span data-ttu-id="9f500-111">![Rautenabhängigkeit](./media/dependencies/diamond-dependency.png "Rautenabhängigkeit")</span><span class="sxs-lookup"><span data-stu-id="9f500-111">![Diamond dependency](./media/dependencies/diamond-dependency.png "Diamond dependency")</span></span>

<span data-ttu-id="9f500-112">Zur Buildzeit analysiert NuGet alle Pakete, von denen ein Projekt abhängig ist, einschließlich der Abhängigkeiten von Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="9f500-112">At build time, NuGet analyzes all the packages that a project depends on, including the dependencies of dependencies.</span></span> <span data-ttu-id="9f500-113">Wenn mehrere Versionen eines Pakets erkannt werden, werden Regeln ausgewertet, um ein Paket auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9f500-113">When multiple versions of a package are detected, rules are evaluated to pick one.</span></span> <span data-ttu-id="9f500-114">Das Vereinheitlichen von Paketen ist notwendig, weil es in .NET problematisch ist, in der gleichen Anwendung verschiedene Versionen einer Assembly nebeneinander auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f500-114">Unifying packages is necessary because running side-by-side versions of an assembly in the same application is problematic in .NET.</span></span>

<span data-ttu-id="9f500-115">Die meisten Rautenabhängigkeiten lassen sich recht einfach auflösen. Unter bestimmten Umständen können sie jedoch Probleme verursachen:</span><span class="sxs-lookup"><span data-stu-id="9f500-115">Most diamond dependencies are easily resolved; however, they can create issues in certain circumstances:</span></span>

1. <span data-ttu-id="9f500-116">**In Konflikt stehende NuGet-Paketverweise** verhindern, dass eine Version während der Paketwiederherstellung aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f500-116">**Conflicting NuGet package references** prevent a version from being resolved during package restore.</span></span>
2. <span data-ttu-id="9f500-117">**Breaking Changes zwischen den Versionen** verursachen Fehler und Ausnahmen während der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="9f500-117">**Breaking changes between the versions** cause bugs and exceptions at runtime.</span></span>
3. <span data-ttu-id="9f500-118">**Die Paketassembly weist einen starken Namen auf**, die Assemblyversion wurde geändert, und die App wird im .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f500-118">**The package assembly is strong named**, the assembly version changed, and the app is running on the .NET Framework.</span></span> <span data-ttu-id="9f500-119">Assemblybindungsumleitungen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9f500-119">Assembly binding redirects are required.</span></span>

<span data-ttu-id="9f500-120">Es ist unmöglich zu bestimmen, welche Pakete neben Ihrem eigenen noch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-120">It's not possible to know what packages will be used alongside your own.</span></span> <span data-ttu-id="9f500-121">Eine gute Möglichkeit, die Wahrscheinlichkeit von Rautenabhängigkeiten für Ihre Bibliothek zu senken, besteht darin, die Anzahl von benötigten Paketen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="9f500-121">A good way to reduce the likelihood of a diamond dependency breaking your library is to minimize the number of packages you depend on.</span></span>

<span data-ttu-id="9f500-122">✔️ Überprüfen Sie Ihre .NET-Bibliothek auf unnötige Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="9f500-122">✔️ DO review your .NET library for unnecessary dependencies.</span></span>

## <a name="nuget-dependency-version-ranges"></a><span data-ttu-id="9f500-123">Versionsbereiche bei NuGet-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="9f500-123">NuGet dependency version ranges</span></span>

<span data-ttu-id="9f500-124">Ein Paketverweis gibt den Bereich gültiger Pakete an, die zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9f500-124">A package reference specifies the range of valid packages it allows.</span></span> <span data-ttu-id="9f500-125">In der Regel ist die Paketverweisversion in der Projektdatei die Mindestversion, und es gibt keine höchste Version.</span><span class="sxs-lookup"><span data-stu-id="9f500-125">Typically, the package reference version in the project file is the minimum version and there's no maximum.</span></span>

```xml
<!-- Accepts any version 1.0 and above. -->
<PackageReference Include="ExamplePackage" Version="1.0" />
```

<span data-ttu-id="9f500-126">Die Regeln, die NuGet zum Auflösen von Abhängigkeiten verwendet, sind [komplex](/nuget/consume-packages/dependency-resolution), aber NuGet sucht immer nach der niedrigsten anwendbaren Version.</span><span class="sxs-lookup"><span data-stu-id="9f500-126">The rules that NuGet uses when resolving dependencies are [complex](/nuget/consume-packages/dependency-resolution), but NuGet always looks for the lowest applicable version.</span></span> <span data-ttu-id="9f500-127">NuGet zieht die niedrigste anwendbare Version der höchsten verfügbaren Version vor, da die niedrigste Version wahrscheinlich die wenigsten Kompatibilitätsprobleme verursachen wird.</span><span class="sxs-lookup"><span data-stu-id="9f500-127">NuGet prefers the lowest applicable version over using the highest available because the lowest will have the least compatibility issues.</span></span>

<span data-ttu-id="9f500-128">Aufgrund der NuGet-Regel, dass immer die niedrigste anwendbare Version verwendet wird, müssen Sie in Paketverweisen weder eine höchste Version noch einen genauen Bereich angeben, um zu vermeiden, dass die letzte Version abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9f500-128">Because of NuGet's lowest applicable version rule, it isn't necessary to place an upper version or exact range on package references to avoid getting the latest version.</span></span> <span data-ttu-id="9f500-129">NuGet versucht bereits, die niedrigste Version mit der höchsten Kompatibilität für Sie zu finden.</span><span class="sxs-lookup"><span data-stu-id="9f500-129">NuGet already tries to find the lowest, most compatible version for you.</span></span>

```xml
<!-- Accepts 1.0 up to 1.x, but not 2.0 and higher. -->
<PackageReference Include="ExamplePackage" Version="[1.0,2.0)" />

<!-- Accepts exactly 1.0. -->
<PackageReference Include="ExamplePackage" Version="[1.0]" />
```

<span data-ttu-id="9f500-130">Obergrenzen für Versionen verursachen einen Fehler in NuGet, wenn ein Konflikt auftritt.</span><span class="sxs-lookup"><span data-stu-id="9f500-130">Upper version limits will cause NuGet to fail if there's a conflict.</span></span> <span data-ttu-id="9f500-131">Ein Beispiel: Eine Bibliothek akzeptiert genau Version 1.0, während eine andere Bibliothek Version 2.0 oder höher erfordert.</span><span class="sxs-lookup"><span data-stu-id="9f500-131">For example, one library accepts exactly 1.0 while another library requires 2.0 or above.</span></span> <span data-ttu-id="9f500-132">Wenn in Version 2.0 Breaking Changes eingeführt wurden, sind bei einer Abhängigkeit, die eine exakte Version oder die höchste verfügbare Version anfordert, Fehler garantiert.</span><span class="sxs-lookup"><span data-stu-id="9f500-132">While breaking changes may have been introduced in version 2.0, a strict or upper limit version dependency guarantees an error.</span></span>

<span data-ttu-id="9f500-133">![Rautenabhängigkeitskonflikt](./media/dependencies/diamond-dependency-conflict.png "Rautenabhängigkeitskonflikt")</span><span class="sxs-lookup"><span data-stu-id="9f500-133">![Diamond dependency conflict](./media/dependencies/diamond-dependency-conflict.png "Diamond dependency conflict")</span></span>

<span data-ttu-id="9f500-134">❌ Verwenden Sie keine NuGet-Paketverweise ohne Mindestversion.</span><span class="sxs-lookup"><span data-stu-id="9f500-134">❌ DO NOT have NuGet package references with no minimum version.</span></span>

<span data-ttu-id="9f500-135">❌ Vermeiden Sie NuGet-Paketverweise, die eine exakte Version erfordern.</span><span class="sxs-lookup"><span data-stu-id="9f500-135">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="9f500-136">❌ Vermeiden Sie NuGet-Paketverweise mit Angabe einer Höchstversion.</span><span class="sxs-lookup"><span data-stu-id="9f500-136">❌ AVOID NuGet package references with a version upper limit.</span></span>

## <a name="nuget-shared-source-packages"></a><span data-ttu-id="9f500-137">NuGet-Pakete mit freigegebenen Quellen</span><span class="sxs-lookup"><span data-stu-id="9f500-137">NuGet shared source packages</span></span>

<span data-ttu-id="9f500-138">Eine Möglichkeit, externe Abhängigkeiten für NuGet-Pakete zu reduzieren, ist der Verweis auf Pakete mit freigegebenen Quellen.</span><span class="sxs-lookup"><span data-stu-id="9f500-138">One way to reduce external NuGet package dependencies is to reference shared source packages.</span></span> <span data-ttu-id="9f500-139">Ein Paket mit freigegebenen Quellen enthält [Quellcodedateien](/nuget/reference/nuspec#including-content-files), die beim Verweisen in ein Projekt einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-139">A shared source package contains [source code files](/nuget/reference/nuspec#including-content-files) that are included in a project when referenced.</span></span> <span data-ttu-id="9f500-140">Da Sie nur Quellcodedateien einbeziehen, die mit dem Rest Ihres Projekts kompiliert werden, gibt es keine externe Abhängigkeit und damit auch keine potenziellen Konflikte.</span><span class="sxs-lookup"><span data-stu-id="9f500-140">Because you're just including source code files that are compiled with the rest of your project, there's no external dependency and chance of conflict.</span></span>

<span data-ttu-id="9f500-141">Pakete mit freigegebenen Quellen eignen sich hervorragend für kleine Funktionsteile.</span><span class="sxs-lookup"><span data-stu-id="9f500-141">Shared source packages are great for including small pieces of functionality.</span></span> <span data-ttu-id="9f500-142">Beispiel: ein Paket mit freigegebenen Quellen mit Hilfsmethoden für das Ausführen von HTTP-Aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9f500-142">For example, a shared source package of helper methods for making HTTP calls.</span></span>

<span data-ttu-id="9f500-143">![Freigegebenes Quellpaket](./media/dependencies/shared-source-package.png "Freigegebenes Quellpaket")</span><span class="sxs-lookup"><span data-stu-id="9f500-143">![Shared source package](./media/dependencies/shared-source-package.png "Shared source package")</span></span>

```xml
<PackageReference Include="Microsoft.Extensions.Buffers.Testing.Sources" PrivateAssets="All" Version="1.0" />
```

<span data-ttu-id="9f500-144">![Freigegebenes Quellprojekt](./media/dependencies/shared-source-project.png "Freigegebenes Quellprojekt")</span><span class="sxs-lookup"><span data-stu-id="9f500-144">![Shared source project](./media/dependencies/shared-source-project.png "Shared source project")</span></span>

<span data-ttu-id="9f500-145">Pakete mit freigegebenen Quellen weisen einige Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="9f500-145">Shared source packages have some limitations.</span></span> <span data-ttu-id="9f500-146">Auf sie kann nur durch `PackageReference` verwiesen werden, ältere `packages.config`-Projekte sind also ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9f500-146">They can only be referenced by `PackageReference`, so older `packages.config` projects are excluded.</span></span> <span data-ttu-id="9f500-147">Pakete mit freigegebenen Quellen können nur von Paketen mit dem gleichen Sprachtyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-147">Also shared source packages are only usable by projects with the same language type.</span></span> <span data-ttu-id="9f500-148">Aufgrund dieser Einschränkungen eignen sich Pakete mit freigegebenen Quellen am besten für die Freigabe von Funktionen in einem Open Source-Projekt.</span><span class="sxs-lookup"><span data-stu-id="9f500-148">Because of these limitations shared source packages are best used to share functionality within an open-source project.</span></span>

<span data-ttu-id="9f500-149">✔️ Erwägen Sie Verweise auf freigegebene Quellen für kleine, interne Funktionsteile.</span><span class="sxs-lookup"><span data-stu-id="9f500-149">✔️ CONSIDER referencing shared source packages for small, internal pieces of functionality.</span></span>

<span data-ttu-id="9f500-150">✔️ Erwägen Sie, Ihr Paket als Paket mit freigegebenen Quellen festzulegen, wenn es kleine, interne Funktionsteile bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9f500-150">✔️ CONSIDER making your package a shared source package if it provides small, internal pieces of functionality.</span></span>

<span data-ttu-id="9f500-151">✔️ Verweisen Sie mit `PrivateAssets="All"` auf Pakete mit freigegebenen Quellen.</span><span class="sxs-lookup"><span data-stu-id="9f500-151">✔️ DO reference shared source packages with `PrivateAssets="All"`.</span></span>

> <span data-ttu-id="9f500-152">Diese Einstellung informiert NuGet darüber, dass das Paket nur während der Entwicklung verwendet werden soll und nicht als öffentliche Abhängigkeit verfügbar gemacht werden darf.</span><span class="sxs-lookup"><span data-stu-id="9f500-152">This setting tells NuGet the package is only to be used at development time and shouldn't be exposed as a public dependency.</span></span>

<span data-ttu-id="9f500-153">❌ Verwenden Sie in Ihrer öffentlichen API keine Pakettypen mit freigegebenen Quellen.</span><span class="sxs-lookup"><span data-stu-id="9f500-153">❌ DO NOT have shared source package types in your public API.</span></span>

> <span data-ttu-id="9f500-154">Pakettypen mit freigegebenen Quellen werden in die verweisende Assembly kompiliert und können nicht über Assemblygrenzen hinweg ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-154">Shared source types are compiled into the referencing assembly and can't be exchanged across assembly boundaries.</span></span> <span data-ttu-id="9f500-155">Ein `IRepository`-Typ mit freigegebenen Quellen in einem Projekt ist ein anderer Typ als der gleiche `IRepository`-Typ mit freigegebenen Quellen in einem anderen Projekt.</span><span class="sxs-lookup"><span data-stu-id="9f500-155">For example, a shared-source `IRepository` type in one project is a separate type from the same shared-source `IRepository` in another project.</span></span> <span data-ttu-id="9f500-156">Für Typen in Paketen mit freigegebenen Quellen sollte die Sichtbarkeit auf `internal` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-156">Types in shared source packages should have an `internal` visibility.</span></span>

<span data-ttu-id="9f500-157">❌ Veröffentlichen Sie keine Pakete mit freigegebenen Quellen in NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="9f500-157">❌ DO NOT publish shared source packages to NuGet.org.</span></span>

> <span data-ttu-id="9f500-158">Pakete mit freigegebenen Quellen enthalten Quellcode und können nur von Projekten mit dem gleichen Sprachtyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-158">Shared source packages contain source code and can only be used by projects with the same language type.</span></span> <span data-ttu-id="9f500-159">Ein in C# geschriebenes Paket mit freigegebenen Quellen kann z.B. nicht von einer F#-Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f500-159">For example, a C# shared source package cannot be used by an F# application.</span></span>
>
> <span data-ttu-id="9f500-160">Veröffentlichen Sie Pakete mit freigegebenen Quellen in einem [lokalen Feed oder in MyGet](./publish-nuget-package.md), um sie intern in Ihrem Projekt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f500-160">Publish shared source packages to a [local feed or MyGet](./publish-nuget-package.md) to consume them internally within your project.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9f500-161">[Zurück](nuget.md)
>[Weiter](sourcelink.md)</span><span class="sxs-lookup"><span data-stu-id="9f500-161">[Previous](nuget.md)
[Next](sourcelink.md)</span></span>
