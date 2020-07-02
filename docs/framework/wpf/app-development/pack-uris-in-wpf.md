---
title: Paket-URIs
description: Erfahren Sie mehr über die vielen Möglichkeiten, URIs (Uniform Resource Identifier) zum Identifizieren und Laden von Dateien in Windows Presentation Foundation (WPF) zu verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 1d19dec0d846659f8de6ed518a7f98d224354a82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621690"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="1046d-103">Paket-URI in WPF</span><span class="sxs-lookup"><span data-stu-id="1046d-103">Pack URIs in WPF</span></span>

<span data-ttu-id="1046d-104">In Windows Presentation Foundation (WPF) werden die URIs (Uniform Resource Identifier) zum Identifizieren und Laden von Dateien in vielerlei Hinsicht verwendet, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1046d-104">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="1046d-105">Angeben der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , die beim ersten Start einer Anwendung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1046d-105">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="1046d-106">Laden von Bildern</span><span class="sxs-lookup"><span data-stu-id="1046d-106">Loading images.</span></span>

- <span data-ttu-id="1046d-107">Navigieren zu Seiten</span><span class="sxs-lookup"><span data-stu-id="1046d-107">Navigating to pages.</span></span>

- <span data-ttu-id="1046d-108">Laden von nicht ausführbaren Datendateien</span><span class="sxs-lookup"><span data-stu-id="1046d-108">Loading non-executable data files.</span></span>

<span data-ttu-id="1046d-109">Darüber hinaus können URIs verwendet werden, um Dateien aus verschiedenen Speicherorten zu identifizieren und zu laden, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1046d-109">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="1046d-110">Die aktuelle Assembly.</span><span class="sxs-lookup"><span data-stu-id="1046d-110">The current assembly.</span></span>

- <span data-ttu-id="1046d-111">Eine Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-111">A referenced assembly.</span></span>

- <span data-ttu-id="1046d-112">Ein zu einer Assembly relativer Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1046d-112">A location relative to an assembly.</span></span>

- <span data-ttu-id="1046d-113">Die Ursprungssite der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1046d-113">The application's site of origin.</span></span>

<span data-ttu-id="1046d-114">Zum Bereitstellen eines konsistenten Mechanismus zum Identifizieren und Laden dieser Dateitypen von diesen Speicherorten nutzt WPF die Erweiterbarkeit des Paket- *URI-Schemas*.</span><span class="sxs-lookup"><span data-stu-id="1046d-114">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="1046d-115">Dieses Thema enthält eine Übersicht über das Schema und erläutert, wie Paket-URIs für eine Vielzahl von Szenarien erstellt werden. es werden absolute und relative URIs und die URI-Auflösung erläutert, bevor gezeigt wird, wie Paket-URIs aus Markup und Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-115">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="1046d-116">Das Paket-URI-Schema</span><span class="sxs-lookup"><span data-stu-id="1046d-116">The Pack URI Scheme</span></span>

<span data-ttu-id="1046d-117">Das Paket-URI-Schema wird von der OPC-Spezifikation ( [Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) ) verwendet, mit der ein Modell zum organisieren und Identifizieren von Inhalten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-117">The pack URI scheme is used by the [Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="1046d-118">Die wichtigsten Elemente dieses Modells sind Pakete und Teile, wobei ein *Paket* ein logischer Container für einen oder mehrere logische *Teile*ist.</span><span class="sxs-lookup"><span data-stu-id="1046d-118">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="1046d-119">Die folgende Abbildung veranschaulicht dieses Konzept.</span><span class="sxs-lookup"><span data-stu-id="1046d-119">The following figure illustrates this concept.</span></span>

![Paket und Teile-Diagramm](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="1046d-121">Zur Identifizierung von Teilen nutzt die OPC-Spezifikation die Erweiterbarkeit von RFC 2396 (Uniform Resource Identifier (URI): generische Syntax), um das Paket-URI-Schema zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1046d-121">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="1046d-122">Das durch einen URI angegebene Schema wird durch das Präfix definiert. "http", "FTP" und "file" sind bekannte Beispiele.</span><span class="sxs-lookup"><span data-stu-id="1046d-122">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="1046d-123">Das Paket-URI-Schema verwendet "Pack" als Schema und enthält zwei Komponenten: Autorität und Pfad.</span><span class="sxs-lookup"><span data-stu-id="1046d-123">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="1046d-124">Im folgenden finden Sie das Format für einen Paket-URI.</span><span class="sxs-lookup"><span data-stu-id="1046d-124">The following is the format for a pack URI.</span></span>

<span data-ttu-id="1046d-125">Pack://*Authority* / *path*</span><span class="sxs-lookup"><span data-stu-id="1046d-125">pack://*authority*/*path*</span></span>

<span data-ttu-id="1046d-126">Die *Autorität* gibt den Pakettyp an, in dem ein Teil enthalten ist, während der *Pfad* den Speicherort eines Teils innerhalb eines Pakets angibt.</span><span class="sxs-lookup"><span data-stu-id="1046d-126">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="1046d-127">Dieses Konzept wird in der folgenden Abbildung verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="1046d-127">This concept is illustrated by the following figure:</span></span>

![Beziehung zwischen Paket, Zertifizierungsstelle und Pfad](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="1046d-129">Pakete und Teile entsprechen Anwendungen und Dateien: eine Anwendung (ein Paket) kann eine oder mehrere Dateien (Teile) enthalten, darunter:</span><span class="sxs-lookup"><span data-stu-id="1046d-129">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="1046d-130">Ressourcendateien, die in die lokale Assembly kompiliert werden</span><span class="sxs-lookup"><span data-stu-id="1046d-130">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="1046d-131">Ressourcendateien, die in eine Assembly kompiliert werden, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-131">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="1046d-132">Ressourcendateien, die in eine verweisende Assembly kompiliert werden</span><span class="sxs-lookup"><span data-stu-id="1046d-132">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="1046d-133">Inhaltsdateien</span><span class="sxs-lookup"><span data-stu-id="1046d-133">Content files.</span></span>

- <span data-ttu-id="1046d-134">Dateien der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="1046d-134">Site of origin files.</span></span>

<span data-ttu-id="1046d-135">Für den Zugriff auf diese Dateitypen unterstützt WPF zwei Autoritäten: Application:///und siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="1046d-135">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="1046d-136">Durch die Autorität „application:///“ werden Anwendungsdatendateien identifiziert, die zur Kompilierungszeit bekannt sind, darunter Ressourcen- und Inhaltsdateien.</span><span class="sxs-lookup"><span data-stu-id="1046d-136">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="1046d-137">Durch die Autorität „siteoforigin:///“ werden die Dateien der Ursprungssite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1046d-137">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="1046d-138">Der Bereich der Autoritäten wird in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1046d-138">The scope of each authority is shown in the following figure.</span></span>

![Paket-URI-Diagramm](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="1046d-140">Die Autoritäts Komponente eines Paket-URIs ist ein eingebetteter URI, der auf ein Paket verweist und RFC 2396 entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="1046d-140">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="1046d-141">Außerdem muss das Zeichen „/“ durch „,“ ersetzt werden, und reservierte Zeichen wie „%“ und „?“ müssen mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-141">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="1046d-142">Ausführliche Informationen finden Sie in der OPC.</span><span class="sxs-lookup"><span data-stu-id="1046d-142">See the OPC for details.</span></span>

<span data-ttu-id="1046d-143">In den folgenden Abschnitten wird erläutert, wie Sie Paket-URIs mit diesen beiden Autorisierungs Methoden in Verbindung mit den entsprechenden Pfaden zum Identifizieren von Ressourcen, Inhalten und Ursprungs Dateien der Ursprungs Site erstellen.</span><span class="sxs-lookup"><span data-stu-id="1046d-143">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="1046d-144">Paket-URIs der Ressourcendatei</span><span class="sxs-lookup"><span data-stu-id="1046d-144">Resource File Pack URIs</span></span>

<span data-ttu-id="1046d-145">Ressourcen Dateien werden als MSBuild `Resource` -Elemente konfiguriert und in Assemblys kompiliert.</span><span class="sxs-lookup"><span data-stu-id="1046d-145">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="1046d-146">WPF unterstützt die Erstellung von Paket-URIs, die verwendet werden können, um Ressourcen Dateien zu identifizieren, die entweder in der lokalen Assembly kompiliert oder in eine Assembly kompiliert werden, auf die von der lokalen Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-146">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="1046d-147">Ressourcendatei der lokalen Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-147">Local Assembly Resource File</span></span>

<span data-ttu-id="1046d-148">Der Paket-URI für eine Ressourcen Datei, die in die lokale Assembly kompiliert wird, verwendet die folgende Autorität und den folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="1046d-148">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="1046d-149">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="1046d-149">**Authority**: application:///.</span></span>

- <span data-ttu-id="1046d-150">**Pfad**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der lokalen Assembly.</span><span class="sxs-lookup"><span data-stu-id="1046d-150">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="1046d-151">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stammverzeichnis des Projekt Ordners der lokalen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="1046d-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="1046d-152">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich in einem Unterordner des Projekt Ordners der lokalen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="1046d-152">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="1046d-153">Ressourcendatei der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-153">Referenced Assembly Resource File</span></span>

<span data-ttu-id="1046d-154">Der Paket-URI für eine Ressourcen Datei, die in eine referenzierte Assembly kompiliert wird, verwendet die folgende Autorität und den folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="1046d-154">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="1046d-155">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="1046d-155">**Authority**: application:///.</span></span>

- <span data-ttu-id="1046d-156">**Pfad**: Der Name einer Ressourcendatei, die in eine Assembly kompiliert wurde, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-156">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="1046d-157">Der Pfad muss dem folgenden Format entsprechen:</span><span class="sxs-lookup"><span data-stu-id="1046d-157">The path must conform to the following format:</span></span>

  <span data-ttu-id="1046d-158">*AssemblyShortName*{*; Version*] {*; PublicKey*]; Komponente/*Pfad*</span><span class="sxs-lookup"><span data-stu-id="1046d-158">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="1046d-159">**AssemblyShortName**: Der Kurzname für die Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-159">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="1046d-160">**;Version** [optional]: Die Version der Assembly, auf die verwiesen wird, die die Ressourcendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="1046d-160">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="1046d-161">Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-161">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="1046d-162">**;PublicKey** [optional]: Der öffentliche Schlüssel, der zum Signieren der Assembly verwendet wird, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-162">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="1046d-163">Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-163">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="1046d-164">**;component**: Gibt an, dass von der lokalen Assembly auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-164">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="1046d-165">**/Path**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-165">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="1046d-166">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stammverzeichnis des Projekt Ordners der referenzierten Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="1046d-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="1046d-167">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich in einem Unterordner des Projekt Ordners der Assembly befindet, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="1046d-168">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcen Datei, die sich im Stamm Ordner des Projekt Ordners einer referenzierten, Versions spezifischen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="1046d-168">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="1046d-169">Beachten Sie, dass die Paket-URI-Syntax für referenzierte assemblyressourcendateien nur mit der Application:///Authority verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1046d-169">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="1046d-170">Beispielsweise wird in WPF Folgendes nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1046d-170">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="1046d-171">Paket-URIs der Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="1046d-171">Content File Pack URIs</span></span>

<span data-ttu-id="1046d-172">Der Paket-URI für eine Inhalts Datei verwendet die folgende Autorität und den folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="1046d-172">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="1046d-173">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="1046d-173">**Authority**: application:///.</span></span>

- <span data-ttu-id="1046d-174">**Pfad**: Der Name der Inhaltsdatei, einschließlich des Pfads, relativ zum Speicherort des Dateisystems der ausführbaren Hauptassembly der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1046d-174">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="1046d-175">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalts Datei, die sich im selben Ordner befindet wie die ausführbare Assembly.</span><span class="sxs-lookup"><span data-stu-id="1046d-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="1046d-176">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhalts Datei, die sich in einem Unterordner befindet, der relativ zur ausführbaren Assembly der Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="1046d-176">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="1046d-177">Auf HTML-Inhalts Dateien kann nicht navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-177">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="1046d-178">Das URI-Schema unterstützt nur die Navigation zu HTML-Dateien, die sich an der Ursprungs Site befinden.</span><span class="sxs-lookup"><span data-stu-id="1046d-178">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="1046d-179">Paket-URIs der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="1046d-179">Site of Origin Pack URIs</span></span>

<span data-ttu-id="1046d-180">Der Paket-URI für eine Ursprungs Site Datei verwendet die folgende Autorität und den folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="1046d-180">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="1046d-181">**Autorität**: siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="1046d-181">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="1046d-182">**Pfad**: Der Name der Datei der Ursprungssite, einschließlich des Pfads, relativ zum Speicherort, von dem die ausführbare Assembly gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1046d-182">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="1046d-183">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungs Site, die an dem Speicherort gespeichert ist, von dem die ausführbare Assembly gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="1046d-184">Das folgende Beispiel zeigt den Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungs Site, die im Unterordner gespeichert ist, der relativ zu dem Speicherort ist, von dem die ausführbare Assembly der Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-184">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="1046d-185">Seitendateien</span><span class="sxs-lookup"><span data-stu-id="1046d-185">Page Files</span></span>

<span data-ttu-id="1046d-186">XAML-Dateien, die als MSBuild-Elemente konfiguriert werden, `Page` werden auf die gleiche Weise wie Ressourcen Dateien in Assemblys kompiliert.</span><span class="sxs-lookup"><span data-stu-id="1046d-186">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="1046d-187">Folglich können MSBuild- `Page` Elemente mithilfe von Paket-URIs für Ressourcen Dateien identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-187">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="1046d-188">Die Typen von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien, die im Allgemeinen als MSBuild-Elemente konfiguriert werden, `Page` haben eines der folgenden Elemente als Stamm Element:</span><span class="sxs-lookup"><span data-stu-id="1046d-188">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="1046d-189">Absolute und relative Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="1046d-189">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="1046d-190">Ein voll qualifizierter Paket-URI enthält das Schema, die Autorität und den Pfad und wird als absoluter Paket-URI angesehen.</span><span class="sxs-lookup"><span data-stu-id="1046d-190">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="1046d-191">Als Vereinfachung für Entwickler [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie mithilfe von Elementen in der Regel geeignete Attribute mit einem relativen Paket-URI festlegen, der nur den Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="1046d-191">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="1046d-192">Sehen Sie sich beispielsweise den folgenden absoluten Paket-URI für eine Ressourcen Datei in der lokalen Assembly an.</span><span class="sxs-lookup"><span data-stu-id="1046d-192">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="1046d-193">Der relative Paket-URI, der auf diese Ressourcen Datei verweist, würde folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="1046d-193">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="1046d-194">Da Dateien der Ursprungs Site nicht Assemblys zugeordnet sind, kann auf diese nur mit absoluten Paket-URIs verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-194">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="1046d-195">Standardmäßig wird ein relativer Paket-URI als relativ zum Speicherort des Markups oder Codes betrachtet, das den Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="1046d-195">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="1046d-196">Wenn jedoch ein führender umgekehrter Schrägstrich verwendet wird, wird der Verweis auf den relativen Paket-URI als relativ zum Stamm der Anwendung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1046d-196">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="1046d-197">Betrachten Sie beispielsweise die folgende Projektstruktur:</span><span class="sxs-lookup"><span data-stu-id="1046d-197">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="1046d-198">Wenn "Page1. XAML einen URI enthält, der auf *root*\subfolder\page2.XAML verweist, kann der Verweis den folgenden relativen Paket-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="1046d-198">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="1046d-199">Wenn "Page1. XAML einen URI enthält, der auf *root*\page2.XAML verweist, kann der Verweis den folgenden relativen Paket-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="1046d-199">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="1046d-200">Paket-URI-Auflösung</span><span class="sxs-lookup"><span data-stu-id="1046d-200">Pack URI Resolution</span></span>

<span data-ttu-id="1046d-201">Das Format von Paket-URIs ermöglicht es, dass Paket-URIs für verschiedene Dateitypen identisch aussehen.</span><span class="sxs-lookup"><span data-stu-id="1046d-201">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="1046d-202">Sehen Sie sich beispielsweise den folgenden absoluten Paket-URI an.</span><span class="sxs-lookup"><span data-stu-id="1046d-202">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="1046d-203">Dieser absolute Paket-URI kann entweder auf eine Ressourcen Datei in der lokalen Assembly oder auf eine Inhalts Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="1046d-203">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="1046d-204">Das gleiche gilt für den folgenden relativen URI.</span><span class="sxs-lookup"><span data-stu-id="1046d-204">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="1046d-205">Um den Typ der Datei zu bestimmen, auf die sich ein Paket-URI bezieht, löst WPF URIs für Ressourcen Dateien in lokalen Assemblys und Inhalts Dateien mithilfe der folgenden Heuristik auf:</span><span class="sxs-lookup"><span data-stu-id="1046d-205">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="1046d-206">Überprüfen Sie die Assemblymetadaten nach einem <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut, das dem Paket-URI entspricht.</span><span class="sxs-lookup"><span data-stu-id="1046d-206">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="1046d-207">Wenn das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut gefunden wird, verweist der Pfad des Paket-URIs auf eine Inhalts Datei.</span><span class="sxs-lookup"><span data-stu-id="1046d-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="1046d-208">Wenn das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut nicht gefunden wird, überprüfen Sie die festgelegten Ressourcen Dateien, die in die lokale Assembly kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-208">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="1046d-209">Wenn eine Ressourcen Datei gefunden wird, die mit dem Pfad des Paket-URIs übereinstimmt, verweist der Pfad des Paket-URIs auf eine Ressourcen Datei.</span><span class="sxs-lookup"><span data-stu-id="1046d-209">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="1046d-210">Wenn die Ressource nicht gefunden wird, ist die intern erstellte <xref:System.Uri> ungültig.</span><span class="sxs-lookup"><span data-stu-id="1046d-210">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="1046d-211">Die URI-Auflösung gilt nicht für URIs, die Folgendes bezeichnen:</span><span class="sxs-lookup"><span data-stu-id="1046d-211">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="1046d-212">Inhalts Dateien in referenzierten Assemblys: diese Dateitypen werden von WPF nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1046d-212">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="1046d-213">Eingebettete Dateien in referenzierten Assemblys: URIs, die diese identifizieren, sind eindeutig, da Sie sowohl den Namen der referenzierten Assembly als auch das `;component` Suffix enthalten.</span><span class="sxs-lookup"><span data-stu-id="1046d-213">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="1046d-214">Dateien der Ursprungs Site: URIs, die diese identifizieren, sind eindeutig, da Sie die einzigen Dateien sind, die mit Paket-URIs identifiziert werden können, die die siteoforigin:///-Autorität enthalten.</span><span class="sxs-lookup"><span data-stu-id="1046d-214">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="1046d-215">Eine Vereinfachung, die die Paket-URI-Auflösung ermöglicht, besteht darin, dass der Code von den Speicherorten von Ressourcen-und Inhalts Dateien sehr unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="1046d-215">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="1046d-216">Wenn Sie z. b. über eine Ressourcen Datei in der lokalen Assembly verfügen, die als Inhalts Datei neu konfiguriert wird, bleibt der Paket-URI für die Ressource unverändert, ebenso wie der Code, der den Paket-URI verwendet.</span><span class="sxs-lookup"><span data-stu-id="1046d-216">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="1046d-217">Programmieren mit Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="1046d-217">Programming with Pack URIs</span></span>

<span data-ttu-id="1046d-218">Viele WPF-Klassen implementieren Eigenschaften, die mit Paket-URIs festgelegt werden können, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="1046d-218">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="1046d-219">Diese Eigenschaften können sowohl im Markup als auch im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-219">These properties can be set from both markup and code.</span></span> <span data-ttu-id="1046d-220">In diesem Abschnitt werden die grundlegenden Konstruktionen beider Varianten beschrieben, und es werden Beispiele für allgemeine Szenarien gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-220">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="1046d-221">Verwenden von Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="1046d-221">Using Pack URIs in Markup</span></span>

<span data-ttu-id="1046d-222">Ein Paket-URI wird in Markup angegeben, indem das-Element eines Attributs mit dem Paket-URI festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-222">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="1046d-223">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1046d-223">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="1046d-224">Tabelle 1 zeigt die verschiedenen absoluten Paket-URIs, die Sie im Markup angeben können.</span><span class="sxs-lookup"><span data-stu-id="1046d-224">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="1046d-225">Tabelle 1: Absolute Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="1046d-225">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="1046d-226">Datei</span><span class="sxs-lookup"><span data-stu-id="1046d-226">File</span></span>|<span data-ttu-id="1046d-227">Absoluter Paket-URI</span><span class="sxs-lookup"><span data-stu-id="1046d-227">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="1046d-228">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-228">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-229">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-229">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-230">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-230">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-231">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-231">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-232">Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-232">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-233">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="1046d-233">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="1046d-234">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-234">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="1046d-235">Datei der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="1046d-235">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="1046d-236">Datei der Ursprungssite im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-236">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="1046d-237">Tabelle 2 zeigt die verschiedenen relativen Paket-URIs, die Sie im Markup angeben können.</span><span class="sxs-lookup"><span data-stu-id="1046d-237">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="1046d-238">Tabelle 2: Relative Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="1046d-238">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="1046d-239">Datei</span><span class="sxs-lookup"><span data-stu-id="1046d-239">File</span></span>|<span data-ttu-id="1046d-240">Relativer Paket-URI</span><span class="sxs-lookup"><span data-stu-id="1046d-240">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="1046d-241">Ressourcendatei in lokaler Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-241">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-242">Ressourcendatei im Unterordner der lokalen Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-242">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-243">Ressourcendatei in Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-243">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-244">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-244">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="1046d-245">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="1046d-245">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="1046d-246">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-246">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="1046d-247">Verwenden von Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="1046d-247">Using Pack URIs in Code</span></span>

<span data-ttu-id="1046d-248">Sie geben einen Paket-URI im Code an, indem Sie die-Klasse instanziieren <xref:System.Uri> und den Paket-URI als Parameter an den-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="1046d-248">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="1046d-249">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1046d-249">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="1046d-250">Standardmäßig betrachtet die- <xref:System.Uri> Klasse Paket-URIs als absolut.</span><span class="sxs-lookup"><span data-stu-id="1046d-250">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="1046d-251">Folglich wird eine Ausnahme ausgelöst, wenn eine Instanz der- <xref:System.Uri> Klasse mit einem relativen Paket-URI erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-251">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="1046d-252">Glücklicherweise akzeptiert die- <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> Überladung des- <xref:System.Uri> Klassenkonstruktors einen Parameter vom Typ <xref:System.UriKind> , mit dem Sie angeben können, ob ein Paket-URI entweder absolut oder relativ ist.</span><span class="sxs-lookup"><span data-stu-id="1046d-252">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="1046d-253">Sie sollten nur <xref:System.UriKind.Absolute> oder angeben <xref:System.UriKind.Relative> , wenn Sie sicher sind, dass der angegebene Paket-URI ein oder der andere ist.</span><span class="sxs-lookup"><span data-stu-id="1046d-253">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="1046d-254">Wenn Sie nicht wissen, welcher Typ von Paket-URI verwendet wird, z. b. Wenn ein Benutzer zur Laufzeit einen Paket-URI eingibt, verwenden Sie <xref:System.UriKind.RelativeOrAbsolute> stattdessen.</span><span class="sxs-lookup"><span data-stu-id="1046d-254">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="1046d-255">Tabelle 3 zeigt die verschiedenen relativen Paket-URIs, die Sie im Code mithilfe von angeben können <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1046d-255">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1046d-256">Tabelle 3: Absolute Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="1046d-256">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="1046d-257">Datei</span><span class="sxs-lookup"><span data-stu-id="1046d-257">File</span></span>|<span data-ttu-id="1046d-258">Absoluter Paket-URI</span><span class="sxs-lookup"><span data-stu-id="1046d-258">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="1046d-259">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-259">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-260">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-260">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-261">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-261">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-262">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-262">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-263">Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-263">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-264">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="1046d-264">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-265">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-265">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-266">Datei der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="1046d-266">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="1046d-267">Datei der Ursprungssite im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-267">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="1046d-268">Tabelle 4 zeigt die verschiedenen relativen Paket-URIs, die Sie im Code mithilfe von angeben können <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1046d-268">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1046d-269">Tabelle 4: Relative Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="1046d-269">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="1046d-270">Datei</span><span class="sxs-lookup"><span data-stu-id="1046d-270">File</span></span>|<span data-ttu-id="1046d-271">Relativer Paket-URI</span><span class="sxs-lookup"><span data-stu-id="1046d-271">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="1046d-272">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-272">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="1046d-273">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="1046d-273">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="1046d-274">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-274">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="1046d-275">Ressourcendatei im Unterordner – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="1046d-275">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="1046d-276">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="1046d-276">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="1046d-277">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="1046d-277">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="1046d-278">Häufige Szenarien mit Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="1046d-278">Common Pack URI Scenarios</span></span>

<span data-ttu-id="1046d-279">In den vorherigen Abschnitten wurde erläutert, wie Paket-URIs zum Identifizieren von Ressourcen, Inhalten und Ursprungs Dateien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1046d-279">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="1046d-280">In WPF werden diese Konstruktionen auf verschiedene Weise verwendet, und in den folgenden Abschnitten werden verschiedene gängige Verwendungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="1046d-280">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="1046d-281">Angeben der Benutzeroberfläche, die beim Starten einer Anwendung angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="1046d-281">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="1046d-282"><xref:System.Windows.Application.StartupUri%2A>Gibt den ersten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an, der angezeigt wird, wenn eine WPF-Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1046d-282"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="1046d-283">Bei eigenständigen Anwendungen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kann ein Fenster sein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-283">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="1046d-284">Eigenständige Anwendungen und XAML-Browser Anwendungen (XBAPs) können auch eine Seite als anfängliche Benutzeroberfläche angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-284">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="1046d-285">Wenn es sich bei der Anwendung um eine eigenständige Anwendung handelt und eine Seite mit angegeben wird, wird von <xref:System.Windows.Application.StartupUri%2A> WPF ein <xref:System.Windows.Navigation.NavigationWindow> zum Hosten der Seite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1046d-285">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="1046d-286">Für XBAPs wird die Seite im Host Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-286">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="1046d-287">Navigieren zu einer Seite</span><span class="sxs-lookup"><span data-stu-id="1046d-287">Navigating to a Page</span></span>

<span data-ttu-id="1046d-288">Im folgenden Beispiel wird das Navigieren zu einer Seite veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1046d-288">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="1046d-289">Weitere Informationen zu den verschiedenen Möglichkeiten zum Navigieren in WPF finden Sie unter [Übersicht](navigation-overview.md)über die Navigation.</span><span class="sxs-lookup"><span data-stu-id="1046d-289">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="1046d-290">Angeben eines Fenstersymbols</span><span class="sxs-lookup"><span data-stu-id="1046d-290">Specifying a Window Icon</span></span>

<span data-ttu-id="1046d-291">Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines URIs das Symbol eines Fensters angeben.</span><span class="sxs-lookup"><span data-stu-id="1046d-291">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="1046d-292">Weitere Informationen finden Sie unter <xref:System.Windows.Window.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="1046d-292">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="1046d-293">Laden von Bild-, Audio- und Videodateien</span><span class="sxs-lookup"><span data-stu-id="1046d-293">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="1046d-294">Mithilfe von WPF können Anwendungen eine Vielzahl von Medientypen verwenden, die alle identifiziert und mit Paket-URIs geladen werden können, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-294">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="1046d-295">Weitere Informationen zum Arbeiten mit Medieninhalten finden Sie unter [Grafiken und Multimedia](../graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="1046d-295">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="1046d-296">Laden eines Ressourcenverzeichnisses von der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="1046d-296">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="1046d-297">Ressourcen Wörterbücher ( <xref:System.Windows.ResourceDictionary> ) können verwendet werden, um Anwendungs Designs zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1046d-297">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="1046d-298">Eine Möglichkeit, Designs zu erstellen und zu verwalten, besteht darin, mehrere Designs als Ressourcenverzeichnisse zu erstellen, die auf der Ursprungssite einer Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="1046d-298">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="1046d-299">Dadurch können Designs hinzugefügt und aktualisiert werden, ohne dass eine Anwendung erneut kompiliert und bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1046d-299">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="1046d-300">Diese Ressourcen Wörterbücher können mithilfe von Paket-URIs identifiziert und geladen werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1046d-300">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="1046d-301">Eine Übersicht über die Designs in WPF finden Sie unter Erstellen von Formaten [und](../../../desktop-wpf/fundamentals/styles-templates-overview.md)Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="1046d-301">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1046d-302">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1046d-302">See also</span></span>

- [<span data-ttu-id="1046d-303">WPF-Anwendungsressource, Inhalts- und Datendateien</span><span class="sxs-lookup"><span data-stu-id="1046d-303">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
