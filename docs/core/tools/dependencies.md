---
title: Verwalten von Abhängigkeiten in .NET Core-Tools
description: Erläutert, wie Abhängigkeiten mit den .NET Core-Tools verwaltet werden können.
ms.date: 03/06/2017
ms.openlocfilehash: e14fa42534d807e2a0fcce1dabe747c18c5166b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733375"
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="1a376-103">Verwalten von Abhängigkeiten mit .NET Core SDK 1.0</span><span class="sxs-lookup"><span data-stu-id="1a376-103">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="1a376-104">Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu „csproj“ und MSBuild wurde auch ein beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdatei und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="1a376-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="1a376-105">Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="1a376-105">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="1a376-106">Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="1a376-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="1a376-107">Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="1a376-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="1a376-108">In diesem Dokument wird der neue Verweistyp beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a376-108">This document describes the new reference type.</span></span> <span data-ttu-id="1a376-109">Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1a376-109">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="1a376-110">Das neue \<PackageReference>-Element</span><span class="sxs-lookup"><span data-stu-id="1a376-110">The new \<PackageReference> element</span></span>
<span data-ttu-id="1a376-111">`<PackageReference>` weist die folgende grundlegende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="1a376-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="1a376-112">Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene Verweistypen bekannt vor.</span><span class="sxs-lookup"><span data-stu-id="1a376-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="1a376-113">Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a376-113">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="1a376-114">Das untergeordnete `<Version>`-Element gibt die abzurufende Version an.</span><span class="sxs-lookup"><span data-stu-id="1a376-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="1a376-115">Die Versionen werden gemäß den [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a376-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="1a376-116">Wenn Ihnen die allgemeine `csproj`-Syntax noch unbekannt ist, finden Sie weitere Informationen in der Dokumentation zu [MSBuild-Projektverweisen](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="1a376-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="1a376-117">Beim Hinzufügen einer Abhängigkeit, die nur für ein bestimmtes Ziel verfügbar ist, werden Bedingungen wie im folgenden Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="1a376-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="1a376-118">Der obige Code bedeutet, dass die Abhängigkeit nur gültig ist, wenn der Build für das angegebene Ziel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1a376-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="1a376-119">`$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1a376-119">The `$(TargetFramework)` in the condition is an MSBuild property that is being set in the project.</span></span> <span data-ttu-id="1a376-120">Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a376-120">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="1a376-121">Hinzufügen einer Abhängigkeit zu Ihrem Projekt</span><span class="sxs-lookup"><span data-stu-id="1a376-121">Adding a dependency to your project</span></span>
<span data-ttu-id="1a376-122">Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a376-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="1a376-123">Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1a376-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="1a376-124">Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="1a376-124">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="1a376-125">Wenn Sie Ihre Projektdatei öffnen, sehen Sie zwei oder mehr `<ItemGroup>`-Knoten.</span><span class="sxs-lookup"><span data-stu-id="1a376-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="1a376-126">Sie werden feststellen, dass einer der Knoten bereits `<PackageReference>`-Elemente aufweist.</span><span class="sxs-lookup"><span data-stu-id="1a376-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="1a376-127">Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder eine neue erstellen. Sie können frei entscheiden, da das Ergebnis gleich sein wird.</span><span class="sxs-lookup"><span data-stu-id="1a376-127">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="1a376-128">In diesem Beispiel verwenden wir die Standardvorlage, die von `dotnet new console` abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1a376-128">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="1a376-129">Dies ist eine einfache Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="1a376-129">This is a simple console application.</span></span> <span data-ttu-id="1a376-130">Wenn wir das Projekt öffnen, suchen wir zuerst nach `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element.</span><span class="sxs-lookup"><span data-stu-id="1a376-130">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="1a376-131">Wir fügen dann Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="1a376-131">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="1a376-132">Anschließend speichern wir das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1a376-132">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="1a376-133">Das vollständige Projekt sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="1a376-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="1a376-134">Entfernen einer Abhängigkeit aus dem Projekt</span><span class="sxs-lookup"><span data-stu-id="1a376-134">Removing a dependency from the project</span></span>
<span data-ttu-id="1a376-135">Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1a376-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
