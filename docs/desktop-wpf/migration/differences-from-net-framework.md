---
title: Unterschiede zwischen .NET Framework und .NET Core
description: Beschreibt die Unterschiede zwischen der .NET Framework-Implementierung von Windows Presentation Foundation (WPF) und .NET Core WPF. Beim Migrieren Ihrer App sollten Sie diese Inkompatibilitäten berücksichtigen.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433133"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="f0b8c-104">Unterschiede in WPF</span><span class="sxs-lookup"><span data-stu-id="f0b8c-104">Differences in WPF</span></span>

<span data-ttu-id="f0b8c-105">In diesem Artikel werden die Unterschiede zwischen Windows Presentation Foundation (WPF) in .NET Core und .NET Framework beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="f0b8c-106">WPF für .NET Core ist ein [Open-Source-Framework,](https://github.com/dotnet/wpf) das aus dem ursprünglichen WPF für .NET Framework-Quellcode gegabelt wird.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="f0b8c-107">Es gibt einige Features von .NET Framework, die .NET Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="f0b8c-108">Weitere Informationen zu nicht unterstützten Technologien finden Sie unter [.NET Framework-Technologien,](../../core/porting/net-framework-tech-unavailable.md)die unter .NET Core nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="f0b8c-109">Projekte im SDK-Stil</span><span class="sxs-lookup"><span data-stu-id="f0b8c-109">SDK-style projects</span></span>

<span data-ttu-id="f0b8c-110">.NET Core verwendet Projektdateien im SDK-Stil.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="f0b8c-111">Diese Projektdateien unterscheiden sich von den herkömmlichen .NET Framework-Projektdateien, die von Visual Studio verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="f0b8c-112">Um Ihre .NET Framework WPF-Apps in .NET Core zu migrieren, müssen Sie Ihre Projekte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="f0b8c-113">Weitere Informationen finden Sie unter [Migrieren von WPF-Apps nach .NET Core 3.0](convert-project-from-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="f0b8c-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="f0b8c-114">NuGet-Paketverweise</span><span class="sxs-lookup"><span data-stu-id="f0b8c-114">NuGet package references</span></span>

<span data-ttu-id="f0b8c-115">Wenn Ihre .NET Framework-App ihre NuGet-Abhängigkeiten in einer *packages.config-Datei* auflistet, migrieren Sie in das [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) folgende Format:</span><span class="sxs-lookup"><span data-stu-id="f0b8c-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="f0b8c-116">Öffnen Sie in Visual Studio den Bereich **Projektmappen-Explorer.**</span><span class="sxs-lookup"><span data-stu-id="f0b8c-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="f0b8c-117">Klicken Sie in Ihrem WPF-Projekt mit der rechten Maustaste auf **packages.config** > **Migrate packages.config to PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![Aktualisieren auf PackageReference](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="f0b8c-119">Es wird ein Dialogfeld angezeigt, in dem berechnete NuGet-Abhängigkeiten der obersten Ebene angezeigt und gefragt werden, welche anderen NuGet-Pakete auf die oberste Ebene heraufgestuft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="f0b8c-120">Wählen Sie **OK** aus, und die Datei *packages.config* wird aus dem Projekt entfernt, und `<PackageReference>` Elemente werden der Projektdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="f0b8c-121">Wenn Ihr `<PackageReference>`Projekt verwendet, werden Pakete nicht lokal in einem *Paketordner* gespeichert, sondern global gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="f0b8c-122">Öffnen Sie die Projektdatei, und entfernen Sie alle `<Analyzer>` Elemente, die auf den Ordner *Pakete* verwiesen haben.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="f0b8c-123">Diese Analysatoren werden automatisch in die NuGet-Paketreferenzen aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="f0b8c-124">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="f0b8c-124">Code Access Security</span></span>

<span data-ttu-id="f0b8c-125">Code Access Security (CAS) wird von .NET Core oder WPF für .NET Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="f0b8c-126">Alle CAS-bezogenen Funktionen werden unter der Annahme von Full-Trust behandelt.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="f0b8c-127">WPF für .NET Core entfernt CAS-bezogenen Code.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="f0b8c-128">Die öffentliche API-Oberfläche dieser Typen ist weiterhin vorhanden, um sicherzustellen, dass Aufrufe dieser Typen erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="f0b8c-129">Öffentlich definierte CAS-bezogene Typen wurden aus den WPF-Assemblys in die CoreFX-Assemblys verschoben.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the CoreFX assemblies.</span></span> <span data-ttu-id="f0b8c-130">Für die WPF-Assemblys ist die Typweiterleitung auf die neue Position der verschobenen Typen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="f0b8c-131">Quellassembly</span><span class="sxs-lookup"><span data-stu-id="f0b8c-131">Source assembly</span></span> | <span data-ttu-id="f0b8c-132">Zielassembly</span><span class="sxs-lookup"><span data-stu-id="f0b8c-132">Target assembly</span></span> | <span data-ttu-id="f0b8c-133">type</span><span class="sxs-lookup"><span data-stu-id="f0b8c-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="f0b8c-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="f0b8c-135">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="f0b8c-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="f0b8c-137">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="f0b8c-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="f0b8c-139">*System.Windows.Extension.dll*</span><span class="sxs-lookup"><span data-stu-id="f0b8c-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="f0b8c-140">Um die Portierungsreibung zu minimieren, wurde die Funktionalität zum Speichern und `XamlAccessLevel` Abrufen von Informationen zu den folgenden Eigenschaften im Typ beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="f0b8c-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f0b8c-141">Next steps</span></span>

- [<span data-ttu-id="f0b8c-142">Erfahren Sie, wie Sie eine .NET Framework WPF-App in .NET Core portieren.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
