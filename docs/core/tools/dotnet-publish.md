---
title: "dotnet-publish-Befehl – .NET Core-CLI"
description: "Der dotnet-publish-Befehl veröffentlicht ein .NET Core-Projekt in ein Verzeichnis."
keywords: dotnet-publish, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8a37b1eacab13682d4f4a2bea2f9ea248cdd9eb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-publish"></a><span data-ttu-id="f4f06-104">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="f4f06-104">dotnet-publish</span></span>

## <a name="name"></a><span data-ttu-id="f4f06-105">Name</span><span class="sxs-lookup"><span data-stu-id="f4f06-105">Name</span></span>

<span data-ttu-id="f4f06-106">`dotnet-publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.</span><span class="sxs-lookup"><span data-stu-id="f4f06-106">`dotnet-publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f4f06-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f4f06-107">Synopsis</span></span>

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="f4f06-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4f06-108">Description</span></span>

<span data-ttu-id="f4f06-109">`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f4f06-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="f4f06-110">Die Ausgabe wird Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="f4f06-110">The output will contain the following:</span></span>

* <span data-ttu-id="f4f06-111">Intermediate Language-Code (IL) in einer Assembly mit einer `*.dll`-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="f4f06-111">Intermediate Language (IL) code in an assembly with a `*.dll` extension.</span></span>
* <span data-ttu-id="f4f06-112">*\*deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="f4f06-112">*\*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="f4f06-113">*\*.runtime.config.json*-Datei, die gemeinsam genutzte Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Garbage Collection-Typ).</span><span class="sxs-lookup"><span data-stu-id="f4f06-113">*\*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="f4f06-114">Die Abhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f4f06-114">The application's dependencies.</span></span> <span data-ttu-id="f4f06-115">Diese werden aus dem NuGet-Cache in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="f4f06-115">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="f4f06-116">Die `dotnet publish`-Ausgabe des Befehls ist bereit für die Bereitstellung auf einem Hostsystem (z.B. ein Server, PC, Mac, Laptops) für die Ausführung und ist der einzige offiziell unterstützte Weg, um die Anwendung für die Bereitstellung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="f4f06-116">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="f4f06-117">Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f4f06-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="f4f06-118">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4f06-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="f4f06-119">Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="f4f06-119">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="f4f06-120">Argumente</span><span class="sxs-lookup"><span data-stu-id="f4f06-120">Arguments</span></span>

`PROJECT` 

<span data-ttu-id="f4f06-121">Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="f4f06-121">The project to publish, which defaults to the current directory if not specified.</span></span> 

## <a name="options"></a><span data-ttu-id="f4f06-122">Optionen</span><span class="sxs-lookup"><span data-stu-id="f4f06-122">Options</span></span>

`-h|--help`

<span data-ttu-id="f4f06-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="f4f06-123">Prints out a short help for the command.</span></span>  

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f4f06-124">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f4f06-124">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f4f06-125">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="f4f06-125">You must specify the target framework in the project file.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="f4f06-126">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f4f06-126">Publishes the application for a given runtime.</span></span> <span data-ttu-id="f4f06-127">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4f06-127">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="f4f06-128">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f4f06-128">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="f4f06-129">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f4f06-129">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f4f06-130">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="f4f06-130">Specifies the path for the output directory.</span></span> <span data-ttu-id="f4f06-131">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="f4f06-131">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="f4f06-132">Konfiguration, die beim Erstellen des Projekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4f06-132">Configuration to use when building the project.</span></span> <span data-ttu-id="f4f06-133">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f4f06-133">The default value is `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="f4f06-134">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="f4f06-134">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f4f06-135">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="f4f06-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f4f06-136">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f4f06-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="f4f06-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f4f06-137">Examples</span></span>

<span data-ttu-id="f4f06-138">Veröffentlicht das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="f4f06-138">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="f4f06-139">Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="f4f06-139">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="f4f06-140">Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:</span><span class="sxs-lookup"><span data-stu-id="f4f06-140">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="f4f06-141">Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).</span><span class="sxs-lookup"><span data-stu-id="f4f06-141">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="f4f06-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4f06-142">See also</span></span>

* [<span data-ttu-id="f4f06-143">Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="f4f06-143">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="f4f06-144">Runtime-ID-Katalog (RID)</span><span class="sxs-lookup"><span data-stu-id="f4f06-144">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

