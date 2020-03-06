---
title: Verwalten von Abhängigkeiten in .NET Core
description: In diesem Artikel wird erläutert, wie Projektabhängigkeiten für eine .NET Core-Anwendung verwaltet werden.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157244"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="8c188-103">Verwalten von Abhängigkeiten in .NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8c188-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="8c188-104">In diesem Artikel wird erläutert, wie Abhängigkeiten durch Bearbeitung der Projektdatei oder mithilfe der CLI hinzugefügt oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8c188-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="8c188-105">Das Element \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="8c188-105">The \<PackageReference> element</span></span>

<span data-ttu-id="8c188-106">Das Projektdateielement `<PackageReference>` weist die folgende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="8c188-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="8c188-107">Das Attribut `Include` gibt die ID des Pakets an, das zum Projekt hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c188-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="8c188-108">Das `Version`-Attribut gibt die abzurufende Version an.</span><span class="sxs-lookup"><span data-stu-id="8c188-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="8c188-109">Versionen werden gemäß der [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.</span><span class="sxs-lookup"><span data-stu-id="8c188-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="8c188-110">Wenn Sie nicht mit der Projektdateisyntax vertraut sind, finden Sie weitere Informationen in der [Referenz zu MSBuild-Projekten](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="8c188-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="8c188-111">Verwenden Sie wie im folgenden Beispiel gezeigt Bedingungen, um eine Abhängigkeit hinzuzufügen, die nur in einem bestimmten Ziel verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="8c188-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="8c188-112">Die Abhängigkeit im obigen Beispiel ist nur dann gültig, wenn der Build für das angegebene Ziel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8c188-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="8c188-113">`$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8c188-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="8c188-114">Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c188-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="8c188-115">Hinzufügen einer Abhängigkeit durch Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="8c188-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="8c188-116">Fügen Sie ein `<PackageReference>`-Element in ein `<ItemGroup>`-Element ein, um eine Abhängigkeit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8c188-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="8c188-117">Sie können zu einem vorhandenen `<ItemGroup>`-Element hinzufügen oder ein neues erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c188-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="8c188-118">Im folgenden Beispiel wird das Standard-Konsolenanwendungsprojekt verwendet, das von `dotnet new console` erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="8c188-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="8c188-119">Hinzufügen einer Abhängigkeit mithilfe der CLI</span><span class="sxs-lookup"><span data-stu-id="8c188-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="8c188-120">Führen Sie den Befehl [dotnet add package](dotnet-add-package.md) wie im folgenden Beispiel gezeigt aus, um eine Abhängigkeit hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8c188-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="8c188-121">Entfernen einer Abhängigkeit durch Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="8c188-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="8c188-122">Entfernen Sie das jeweilige `<PackageReference>`-Element aus der Projektdatei, um eine Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8c188-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="8c188-123">Entfernen einer Abhängigkeit mithilfe der CLI</span><span class="sxs-lookup"><span data-stu-id="8c188-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="8c188-124">Führen Sie den Befehl [dotnet remove package](dotnet-remove-package.md) wie im folgenden Beispiel gezeigt aus, um eine Abhängigkeit zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8c188-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="8c188-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c188-125">See also</span></span>

* [<span data-ttu-id="8c188-126">NuGet-Pakete in Projektdateien</span><span class="sxs-lookup"><span data-stu-id="8c188-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="8c188-127">[dotnet list package-Befehl](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="8c188-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
