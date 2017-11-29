---
title: "Verwalten von Abhängigkeiten in .NET Core-Tools"
description: "Erläutert, wie Abhängigkeiten mit den .NET Core-Tools verwaltet werden können."
keywords: CLI, Erweiterbarkeit, benutzerdefinierte Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
ms.openlocfilehash: 21f42bbf4693c78a5be271b7769ef4489ed6d476
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="6bb7f-104">Verwalten von Abhängigkeiten mit .NET Core SDK 1.0</span><span class="sxs-lookup"><span data-stu-id="6bb7f-104">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="6bb7f-105">Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu „csproj“ und MSBuild wurde auch ein beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdatei und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-105">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="6bb7f-106">Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-106">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="6bb7f-107">Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-107">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="6bb7f-108">Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-108">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="6bb7f-109">In diesem Dokument wird der neue Verweistyp beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-109">This document describes the new reference type.</span></span> <span data-ttu-id="6bb7f-110">Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-110">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="6bb7f-111">Das neue \<PackageReference>-Element</span><span class="sxs-lookup"><span data-stu-id="6bb7f-111">The new \<PackageReference> element</span></span>
<span data-ttu-id="6bb7f-112">`<PackageReference>` weist die folgende grundlegende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="6bb7f-112">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="6bb7f-113">Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene Verweistypen bekannt vor.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-113">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="6bb7f-114">Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-114">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="6bb7f-115">Das untergeordnete `<Version>`-Element gibt die abzurufende Version an.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-115">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="6bb7f-116">Die Versionen werden gemäß den [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-116">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="6bb7f-117">Wenn Ihnen die allgemeine `csproj`-Syntax noch unbekannt ist, finden Sie weitere Informationen in der Dokumentation zu [MSBuild-Projektverweisen](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="6bb7f-117">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="6bb7f-118">Beim Hinzufügen einer Abhängigkeit, die nur für ein bestimmtes Ziel verfügbar ist, werden Bedingungen wie im folgenden Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="6bb7f-118">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="6bb7f-119">Der obige Code bedeutet, dass die Abhängigkeit nur gültig ist, wenn der Build für das angegebene Ziel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-119">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="6bb7f-120">`$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-120">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="6bb7f-121">Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-121">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="6bb7f-122">Hinzufügen einer Abhängigkeit zu Ihrem Projekt</span><span class="sxs-lookup"><span data-stu-id="6bb7f-122">Adding a dependency to your project</span></span>
<span data-ttu-id="6bb7f-123">Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-123">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="6bb7f-124">Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-124">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="6bb7f-125">Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-125">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="6bb7f-126">Wenn Sie Ihre Projektdatei öffnen, sehen Sie zwei oder mehr `<ItemGroup>`-Knoten.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-126">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="6bb7f-127">Sie werden feststellen, dass einer der Knoten bereits `<PackageReference>`-Elemente aufweist.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-127">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="6bb7f-128">Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder eine neue erstellen. Sie können frei entscheiden, da das Ergebnis gleich sein wird.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-128">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="6bb7f-129">In diesem Beispiel verwenden wir die Standardvorlage, die von `dotnet new console` abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-129">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="6bb7f-130">Dies ist eine einfache Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-130">This is a simple console application.</span></span> <span data-ttu-id="6bb7f-131">Wenn wir das Projekt öffnen, suchen wir zuerst nach `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-131">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="6bb7f-132">Wir fügen dann Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="6bb7f-132">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="6bb7f-133">Anschließend speichern wir das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-133">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="6bb7f-134">Das vollständige Projekt sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="6bb7f-134">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="6bb7f-135">Entfernen einer Abhängigkeit aus dem Projekt</span><span class="sxs-lookup"><span data-stu-id="6bb7f-135">Removing a dependency from the project</span></span>
<span data-ttu-id="6bb7f-136">Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6bb7f-136">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
