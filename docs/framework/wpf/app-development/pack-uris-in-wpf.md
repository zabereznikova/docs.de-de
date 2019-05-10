---
title: Paket-URI in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: d15bb7ab494b5de3c0c37077048beb1527e330a2
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912395"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="00806-102">Paket-URI in WPF</span><span class="sxs-lookup"><span data-stu-id="00806-102">Pack URIs in WPF</span></span>
<span data-ttu-id="00806-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] werden verwendet, um zu identifizieren und Laden von Dateien in vielerlei Hinsicht, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="00806-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] are used to identify and load files in many ways, including the following:</span></span>  
  
- <span data-ttu-id="00806-104">Angeben der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] anzuzeigenden beim ersten Starten einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="00806-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>  
  
- <span data-ttu-id="00806-105">Laden von Bildern</span><span class="sxs-lookup"><span data-stu-id="00806-105">Loading images.</span></span>  
  
- <span data-ttu-id="00806-106">Navigieren zu Seiten</span><span class="sxs-lookup"><span data-stu-id="00806-106">Navigating to pages.</span></span>  
  
- <span data-ttu-id="00806-107">Laden von nicht ausführbaren Datendateien</span><span class="sxs-lookup"><span data-stu-id="00806-107">Loading non-executable data files.</span></span>  
  
 <span data-ttu-id="00806-108">Darüber hinaus [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] kann verwendet werden, um zu identifizieren und Laden von Dateien aus einer Vielzahl von Standorten, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="00806-108">Furthermore, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] can be used to identify and load files from a variety of locations, including the following:</span></span>  
  
- <span data-ttu-id="00806-109">Die aktuelle Assembly.</span><span class="sxs-lookup"><span data-stu-id="00806-109">The current assembly.</span></span>  
  
- <span data-ttu-id="00806-110">Eine Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00806-110">A referenced assembly.</span></span>  
  
- <span data-ttu-id="00806-111">Ein zu einer Assembly relativer Speicherort.</span><span class="sxs-lookup"><span data-stu-id="00806-111">A location relative to an assembly.</span></span>  
  
- <span data-ttu-id="00806-112">Die Ursprungssite der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="00806-112">The application's site of origin.</span></span>  
  
 <span data-ttu-id="00806-113">Um einen einheitlichen Mechanismus zum Identifizieren und laden diese Arten von Dateien in diesen Speicherorten bieten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nutzt die Erweiterbarkeit von der *Paket-URI-Schema*.</span><span class="sxs-lookup"><span data-stu-id="00806-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="00806-114">Dieses Thema bietet eine Übersicht über das Schema, wird beschrieben, wie Sie Paket-erstellen [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für eine Vielzahl von Szenarien, erläutert werden, Absolute und Relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] und [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Auflösung, bevor die zeigt, wie Sie Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] aus beiden Markup und Code.</span><span class="sxs-lookup"><span data-stu-id="00806-114">This topic provides an overview of the scheme, covers how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for a variety of scenarios, discusses absolute and relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] and [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution, before showing how to use pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] from both markup and code.</span></span>  

<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a><span data-ttu-id="00806-115">Das Paket-URI-Schema</span><span class="sxs-lookup"><span data-stu-id="00806-115">The Pack URI Scheme</span></span>  
 <span data-ttu-id="00806-116">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema wird verwendet, durch die [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC)-Spezifikation, die ein Modell zum Organisieren und Identifizieren von Inhalt beschreibt.</span><span class="sxs-lookup"><span data-stu-id="00806-116">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="00806-117">Die wichtigsten Elemente dieses Modells sind Pakete und Teile, wobei eine *Paket* ist ein logischer Container, für ein oder mehr logische *Teile*.</span><span class="sxs-lookup"><span data-stu-id="00806-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="00806-118">Die folgende Abbildung veranschaulicht dieses Konzept.</span><span class="sxs-lookup"><span data-stu-id="00806-118">The following figure illustrates this concept.</span></span>  
  
 ![Paket und Teile-Diagramm](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)  
  
 <span data-ttu-id="00806-120">Um Komponenten zu identifizieren, nutzt die OPC-Spezifikation die Erweiterbarkeit von RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) definieren Sie das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema.</span><span class="sxs-lookup"><span data-stu-id="00806-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme.</span></span>  
  
 <span data-ttu-id="00806-121">Das Schema, das angegeben wird ein [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] wird definiert durch sein Präfix; http, ftp und Datei sind bekannte Beispiele.</span><span class="sxs-lookup"><span data-stu-id="00806-121">The scheme that is specified by a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="00806-122">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Schema verwendet "Paket" als Schema und enthält zwei Komponenten: Autorität und folgenden Pfad.</span><span class="sxs-lookup"><span data-stu-id="00806-122">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="00806-123">Im folgenden finden Sie das Format für ein Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-123">The following is the format for a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 <span data-ttu-id="00806-124">pack://*authority*/*path*</span><span class="sxs-lookup"><span data-stu-id="00806-124">pack://*authority*/*path*</span></span>
  
 <span data-ttu-id="00806-125">Die *Autorität* gibt den Typ des Pakets, das ein Teil enthalten ist, während die *Pfad* gibt den Speicherort eines Elements innerhalb eines Pakets.</span><span class="sxs-lookup"><span data-stu-id="00806-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>  
  
 <span data-ttu-id="00806-126">Dieses Konzept wird in der folgenden Abbildung verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="00806-126">This concept is illustrated by the following figure:</span></span>  
  
 ![Beziehung zwischen Paket, Zertifizierungsstelle und Pfad](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)  
  
 <span data-ttu-id="00806-128">Pakete und Teile entsprechen Anwendungen und Dateien: eine Anwendung (ein Paket) kann eine oder mehrere Dateien (Teile) enthalten, darunter:</span><span class="sxs-lookup"><span data-stu-id="00806-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>  
  
- <span data-ttu-id="00806-129">Ressourcendateien, die in die lokale Assembly kompiliert werden</span><span class="sxs-lookup"><span data-stu-id="00806-129">Resource files that are compiled into the local assembly.</span></span>  
  
- <span data-ttu-id="00806-130">Ressourcendateien, die in eine Assembly kompiliert werden, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-130">Resource files that are compiled into a referenced assembly.</span></span>  
  
- <span data-ttu-id="00806-131">Ressourcendateien, die in eine verweisende Assembly kompiliert werden</span><span class="sxs-lookup"><span data-stu-id="00806-131">Resource files that are compiled into a referencing assembly.</span></span>  
  
- <span data-ttu-id="00806-132">Inhaltsdateien</span><span class="sxs-lookup"><span data-stu-id="00806-132">Content files.</span></span>  
  
- <span data-ttu-id="00806-133">Dateien der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="00806-133">Site of origin files.</span></span>  
  
 <span data-ttu-id="00806-134">Diese Arten von Dateien, den Zugriff auf [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] unterstützt zwei Autoritäten: Application: / / / und Siteoforigin: / / /.</span><span class="sxs-lookup"><span data-stu-id="00806-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="00806-135">Durch die Autorität „application:///“ werden Anwendungsdatendateien identifiziert, die zur Kompilierungszeit bekannt sind, darunter Ressourcen- und Inhaltsdateien.</span><span class="sxs-lookup"><span data-stu-id="00806-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="00806-136">Durch die Autorität „siteoforigin:///“ werden die Dateien der Ursprungssite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="00806-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="00806-137">Der Bereich der Autoritäten wird in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="00806-137">The scope of each authority is shown in the following figure.</span></span>  
  
 ![Paket-URI-Diagramm](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)  
  
> [!NOTE]
>  <span data-ttu-id="00806-139">Die Autoritätskomponente eines Packs [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ist ein eingebetteter [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die auf ein Paket verweist und RFC 2396 entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="00806-139">The authority component of a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is an embedded [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="00806-140">Außerdem muss das Zeichen „/“ durch „,“ ersetzt werden, und reservierte Zeichen wie „%“ und „?“ müssen mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="00806-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="00806-141">Ausführliche Informationen finden Sie in der OPC.</span><span class="sxs-lookup"><span data-stu-id="00806-141">See the OPC for details.</span></span>  
  
 <span data-ttu-id="00806-142">In den folgenden Abschnitten wird erläutert, wie Sie Paket-erstellen [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] mit diesen beiden Autoritäten in Verbindung mit den entsprechenden Pfaden zum Identifizieren von Ressourcen, Inhalte und Dateien der Ursprungssite.</span><span class="sxs-lookup"><span data-stu-id="00806-142">The following sections explain how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a><span data-ttu-id="00806-143">Paket-URIs der Ressourcendatei</span><span class="sxs-lookup"><span data-stu-id="00806-143">Resource File Pack URIs</span></span>  
 <span data-ttu-id="00806-144">Ressourcendateien sind als konfiguriert [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` Elemente und werden in Assemblys kompiliert.</span><span class="sxs-lookup"><span data-stu-id="00806-144">Resource files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` items and are compiled into assemblies.</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="00806-145">unterstützt die Erstellung von Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , die verwendet werden kann, um Ressourcendateien zu identifizieren, die entweder in die lokale Assembly kompiliert oder in einer Assembly, die von der lokalen Assembly verwiesen wird kompiliert.</span><span class="sxs-lookup"><span data-stu-id="00806-145">supports the construction of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a><span data-ttu-id="00806-146">Ressourcendatei der lokalen Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-146">Local Assembly Resource File</span></span>  
 <span data-ttu-id="00806-147">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressource, die in die lokale Assembly kompiliert wird verwendet, folgende Autorität und folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="00806-147">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>  
  
- <span data-ttu-id="00806-148">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="00806-148">**Authority**: application:///.</span></span>  
  
- <span data-ttu-id="00806-149">**Pfad**: Der Name der Ressourcendatei, einschließlich seines Pfads, relativ zum Stammverzeichnis des Projektordners lokalen Assembly.</span><span class="sxs-lookup"><span data-stu-id="00806-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>  
  
 <span data-ttu-id="00806-150">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcendatei, die im Stammverzeichnis des Projektordners der lokalen Assembly gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00806-150">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="00806-151">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcendatei, die in einem Unterordner des Projektordners der lokalen Assembly gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00806-151">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="00806-152">Ressourcendatei der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-152">Referenced Assembly Resource File</span></span>  
 <span data-ttu-id="00806-153">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressource, die in einer referenzierten Assembly kompiliert wird verwendet, folgende Autorität und folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="00806-153">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>  
  
- <span data-ttu-id="00806-154">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="00806-154">**Authority**: application:///.</span></span>  
  
- <span data-ttu-id="00806-155">**Pfad**: Der Name einer Ressourcendatei, die in einer referenzierten Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="00806-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="00806-156">Der Pfad muss dem folgenden Format entsprechen:</span><span class="sxs-lookup"><span data-stu-id="00806-156">The path must conform to the following format:</span></span>  
  
     <span data-ttu-id="00806-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span><span class="sxs-lookup"><span data-stu-id="00806-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>  
  
    - <span data-ttu-id="00806-158">**AssemblyShortName**: Der Kurzname für die Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00806-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>  
  
    - <span data-ttu-id="00806-159">**;Version** [optional]: Die Version der Assembly, auf die verwiesen wird, die die Ressourcendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="00806-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="00806-160">Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.</span><span class="sxs-lookup"><span data-stu-id="00806-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    - <span data-ttu-id="00806-161">**;PublicKey** [optional]: Der öffentliche Schlüssel, der zum Signieren der Assembly verwendet wird, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00806-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="00806-162">Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.</span><span class="sxs-lookup"><span data-stu-id="00806-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    - <span data-ttu-id="00806-163">**;component**: Gibt an, dass von der lokalen Assembly auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00806-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>  
  
    - <span data-ttu-id="00806-164">**/Path**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00806-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>  
  
 <span data-ttu-id="00806-165">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcendatei, die im Stammverzeichnis des Projektordners der Assembly, auf die verwiesen wird, gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00806-165">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 <span data-ttu-id="00806-166">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcendatei, die in einem Unterordner des Projektordners der Assembly, auf die verwiesen wird, gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00806-166">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 <span data-ttu-id="00806-167">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ressourcendatei, die im Stammverzeichnis des Projektordners ein auf die verwiesen wird, hängt von der Version der Assembly gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00806-167">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 <span data-ttu-id="00806-168">Beachten Sie, dass das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Syntax für Ressourcendateien einer Assembly verwiesen wird, kann nur mit der Anwendung verwendet werden: / / / der Autorität.</span><span class="sxs-lookup"><span data-stu-id="00806-168">Note that the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="00806-169">Beispielsweise wird Folgendes nicht unterstützt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a><span data-ttu-id="00806-170">Paket-URIs der Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="00806-170">Content File Pack URIs</span></span>  
 <span data-ttu-id="00806-171">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Inhaltsdatei, folgende Autorität und folgenden Pfad verwendet:</span><span class="sxs-lookup"><span data-stu-id="00806-171">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a content file uses the following authority and path:</span></span>  
  
- <span data-ttu-id="00806-172">**Autorität**: application:///.</span><span class="sxs-lookup"><span data-stu-id="00806-172">**Authority**: application:///.</span></span>  
  
- <span data-ttu-id="00806-173">**Pfad**: Der Name der Inhaltsdatei, einschließlich seines Pfads relativ zu den Dateisystempfad der ausführbaren Hauptassembly der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="00806-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>  
  
 <span data-ttu-id="00806-174">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhaltsdatei, die sich im selben Ordner wie die ausführbare Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="00806-174">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 <span data-ttu-id="00806-175">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Inhaltsdatei, die in einem Unterordner, der relativ zur ausführbaren Assembly der Anwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00806-175">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="00806-176">Zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]-Inhaltsdateien kann nicht navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="00806-176">[!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] content files cannot be navigated to.</span></span> <span data-ttu-id="00806-177">Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] -Schema unterstützt nur die Navigation zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Dateien, die auf der Ursprungssite gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="00806-177">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme only supports navigation to [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] files that are located at the site of origin.</span></span>  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="00806-178">Paket-URIs der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="00806-178">Site of Origin Pack URIs</span></span>  
 <span data-ttu-id="00806-179">Das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ursprungssite-Datei verwendet folgende Autorität und folgenden Pfad:</span><span class="sxs-lookup"><span data-stu-id="00806-179">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a site of origin file uses the following authority and path:</span></span>  
  
- <span data-ttu-id="00806-180">**Autorität**: siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="00806-180">**Authority**: siteoforigin:///.</span></span>  
  
- <span data-ttu-id="00806-181">**Pfad**: Der Name des Standorts-Datei der Ursprungssite, einschließlich seines Pfads relativ zum Speicherort, an dem die ausführbare Assembly gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="00806-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>  
  
 <span data-ttu-id="00806-182">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungssite, an dem Speicherort, von dem die ausführbare Assembly gestartet wird, gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00806-182">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 <span data-ttu-id="00806-183">Das folgende Beispiel zeigt den Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei der Ursprungssite, gespeichert in Unterordner, der relativ zum Speicherort wird von dem ausführbare Assembly der Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="00806-183">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a><span data-ttu-id="00806-184">Seitendateien</span><span class="sxs-lookup"><span data-stu-id="00806-184">Page Files</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="00806-185">Dateien, die als konfiguriert sind [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` Elemente werden in Assemblys kompiliert, auf die gleiche Weise wie Ressourcendateien.</span><span class="sxs-lookup"><span data-stu-id="00806-185">files that are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="00806-186">Folglich [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` Elemente können Sie anhand Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für Ressourcendateien.</span><span class="sxs-lookup"><span data-stu-id="00806-186">Consequently, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items can be identified using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files.</span></span>  
  
 <span data-ttu-id="00806-187">Die Typen von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien, die häufig als konfiguriert sind [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` Elemente weisen einen der folgenden als Stammelement:</span><span class="sxs-lookup"><span data-stu-id="00806-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items have one of the following as their root element:</span></span>  
  
- <xref:System.Windows.Window?displayProperty=nameWithType>  
  
- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="00806-188">Absolute und relative Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="00806-188">Absolute vs. Relative Pack URIs</span></span>  
 <span data-ttu-id="00806-189">Ein vollqualifizierter Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] enthält das Schema, die Autorität und dem Pfad, und es wird als absoluter Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-189">A fully qualified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] includes the scheme, the authority, and the path, and it is considered an absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="00806-190">Als eine Vereinfachung für Entwickler [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Elemente ermöglichen normalerweise Festlegen entsprechender Attribute mit einem relativen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], die nur den Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="00806-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which includes only the path.</span></span>  
  
 <span data-ttu-id="00806-191">Betrachten Sie z. B. der folgenden absoluten Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcendatei in der lokalen Assembly.</span><span class="sxs-lookup"><span data-stu-id="00806-191">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file in the local assembly.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="00806-192">Der relative Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die auf diese Ressource verweist Datei wäre.</span><span class="sxs-lookup"><span data-stu-id="00806-192">The relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that refers to this resource file would be the following.</span></span>  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="00806-193">Da Dateien der Ursprungssite nicht mit Assemblys verknüpft sind, sie können nur verwiesen werden mit absoluten Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="00806-194">Standardmäßig wird eine relative Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] gilt relativ zum Speicherort des Markup oder Code, der den Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="00806-194">By default, a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="00806-195">Wenn ein vorangestellter umgekehrter Schrägstrich verwendet wird, aber die relativen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Verweis wird dann als relativ zum Stammverzeichnis der Anwendung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="00806-195">If a leading backslash is used, however, the relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="00806-196">Betrachten Sie beispielsweise die folgende Projektstruktur:</span><span class="sxs-lookup"><span data-stu-id="00806-196">For example, consider the following project structure.</span></span>  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 <span data-ttu-id="00806-197">Wenn "Page1.xaml" enthält einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die auf *Stamm*\SubFolder\Page2.xaml, der Verweis können Sie den folgenden relativen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-197">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `Page2.xaml`  
  
 <span data-ttu-id="00806-198">Wenn "Page1.xaml" enthält einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , die auf *Stamm*\Page2.xaml, der Verweis können Sie den folgenden relativen Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-198">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a><span data-ttu-id="00806-199">Paket-URI-Auflösung</span><span class="sxs-lookup"><span data-stu-id="00806-199">Pack URI Resolution</span></span>  
 <span data-ttu-id="00806-200">Das Format des Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ermöglicht es dem Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für verschiedene Arten von Dateien identisch aussehen.</span><span class="sxs-lookup"><span data-stu-id="00806-200">The format of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] makes it possible for pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for different types of files to look the same.</span></span> <span data-ttu-id="00806-201">Betrachten Sie z. B. der folgenden absoluten Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-201">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="00806-202">Dieser absolute Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] kann entweder eine Ressourcendatei in der lokalen Assembly oder eine Inhaltsdatei verweisen.</span><span class="sxs-lookup"><span data-stu-id="00806-202">This absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="00806-203">Das gleiche gilt für folgenden relativen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-203">The same is true for the following relative [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="00806-204">Um zu ermitteln, der Typ der Datei, die ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verweist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] löst [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für Ressourcendateien in lokalen Assemblys und Inhaltsdateien mit folgender Heuristik:</span><span class="sxs-lookup"><span data-stu-id="00806-204">In order to determine the type of file that a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files in local assemblies and content files by using the following heuristics:</span></span>  
  
1. <span data-ttu-id="00806-205">Überprüfen der Assemblymetadaten auf ein <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> -Attribut, das Pack entspricht [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
2. <span data-ttu-id="00806-206">Wenn die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut gefunden wird, wird der Pfad des Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bezieht sich auf eine Inhaltsdatei.</span><span class="sxs-lookup"><span data-stu-id="00806-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a content file.</span></span>  
  
3. <span data-ttu-id="00806-207">Wenn die <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Attribut wurde nicht gefunden, überprüfen die festgelegten Ressourcendateien, die in die lokale Assembly kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="00806-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>  
  
4. <span data-ttu-id="00806-208">Wenn eine Ressourcendatei, die den Pfad des Paket-entspricht [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] gefunden wird, wird der Pfad des Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bezieht sich auf eine Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="00806-208">If a resource file that matches the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a resource file.</span></span>  
  
5. <span data-ttu-id="00806-209">Wenn die Ressource nicht gefunden wird, der intern erstellte <xref:System.Uri> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="00806-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <span data-ttu-id="00806-210">-Auflösung gilt nicht für [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] mit Verweisen auf die folgenden:</span><span class="sxs-lookup"><span data-stu-id="00806-210">resolution does not apply for [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that refer to the following:</span></span>  
  
- <span data-ttu-id="00806-211">Inhaltsdateien in Assemblys verwiesen wird: Diese Dateitypen werden nicht unterstützt, indem [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
- <span data-ttu-id="00806-212">Eingebettete Dateien in Assemblys verwiesen wird: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , identifizieren sie eindeutig sind, da sie den Namen der referenzierten Assembly enthalten und die `;component` Suffix.</span><span class="sxs-lookup"><span data-stu-id="00806-212">Embedded files in referenced assemblies: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>  
  
- <span data-ttu-id="00806-213">Dateien der Ursprungssite: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , identifizieren sie eindeutig sind, da sie die einzigen Dateien sind, die vom Pack identifiziert werden können [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , enthalten die Siteoforigin: / / / der Autorität.</span><span class="sxs-lookup"><span data-stu-id="00806-213">Site of origin files: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they are the only files that can be identified by pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that contain the siteoforigin:/// authority.</span></span>  
  
 <span data-ttu-id="00806-214">Eine Vereinfachung, die pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Auflösung kann für Code ein wenig von den Speicherorten der Ressourcen-und Inhaltsdateien unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="00806-214">One simplification that pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="00806-215">Wenn Sie eine Ressourcendatei in der lokalen Assembly haben, umkonfiguriert wird, um eine Inhaltsdatei, die das Pack werden z. B. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die Ressource unverändert bleibt, wie der Code, der die Pack verwendet [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the resource remains the same, as does the code that uses the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a><span data-ttu-id="00806-216">Programmieren mit Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="00806-216">Programming with Pack URIs</span></span>  
 <span data-ttu-id="00806-217">Viele [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Klassen implementieren Eigenschaften, die mit Pack festgelegt werden, können [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], einschließlich:</span><span class="sxs-lookup"><span data-stu-id="00806-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including:</span></span>  
  
- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="00806-218">Diese Eigenschaften können sowohl im Markup als auch im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="00806-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="00806-219">In diesem Abschnitt werden die grundlegenden Konstruktionen beider Varianten beschrieben, und es werden Beispiele für allgemeine Szenarien gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00806-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="00806-220">Verwenden von Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="00806-220">Using Pack URIs in Markup</span></span>  
 <span data-ttu-id="00806-221">Ein Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] im Markup angegeben ist, durch Festlegen des Elements eines Attributs mit dem Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-221">A pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is specified in markup by setting the element of an attribute with the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="00806-222">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00806-222">For example:</span></span>  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 <span data-ttu-id="00806-223">Tabelle 1 sehen Sie die verschiedenen absolute Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , die Sie im Markup angeben können.</span><span class="sxs-lookup"><span data-stu-id="00806-223">Table 1 illustrates the various absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="00806-224">Tabelle 1: Absolute Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="00806-224">Table 1: Absolute Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="00806-225">Datei</span><span class="sxs-lookup"><span data-stu-id="00806-225">File</span></span>|<span data-ttu-id="00806-226">Absolute Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00806-226">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="00806-227">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-228">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-229">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-230">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-231">Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-232">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="00806-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|  
|<span data-ttu-id="00806-233">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|<span data-ttu-id="00806-234">Datei der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="00806-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|<span data-ttu-id="00806-235">Datei der Ursprungssite im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 <span data-ttu-id="00806-236">Tabelle 2 sehen Sie die verschiedenen relative Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , die Sie im Markup angeben können.</span><span class="sxs-lookup"><span data-stu-id="00806-236">Table 2 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="00806-237">Tabelle 2: Relative Paket-URIs im Markup</span><span class="sxs-lookup"><span data-stu-id="00806-237">Table 2: Relative Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="00806-238">Datei</span><span class="sxs-lookup"><span data-stu-id="00806-238">File</span></span>|<span data-ttu-id="00806-239">Relative Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00806-239">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="00806-240">Ressourcendatei in lokaler Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-241">Ressourcendatei im Unterordner der lokalen Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-242">Ressourcendatei in Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-243">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="00806-244">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="00806-244">Content file</span></span>|`"/ContentFile.xaml"`|  
|<span data-ttu-id="00806-245">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a><span data-ttu-id="00806-246">Verwenden von Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="00806-246">Using Pack URIs in Code</span></span>  
 <span data-ttu-id="00806-247">Sie geben einen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] im Code durch Instanziierung der <xref:System.Uri> -Klasse und übergeben das Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als Parameter an den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="00806-247">You specify a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in code by instantiating the <xref:System.Uri> class and passing the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as a parameter to the constructor.</span></span> <span data-ttu-id="00806-248">Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00806-248">This is demonstrated in the following example.</span></span>  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 <span data-ttu-id="00806-249">In der Standardeinstellung die <xref:System.Uri> -Klasse Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] als absolut an.</span><span class="sxs-lookup"><span data-stu-id="00806-249">By default, the <xref:System.Uri> class considers pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to be absolute.</span></span> <span data-ttu-id="00806-250">Daher wird eine Ausnahme ausgelöst, wenn eine Instanz von der <xref:System.Uri> Klasse wird erstellt, mit einem relativen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00806-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 <span data-ttu-id="00806-251">Glücklicherweise die <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> Überladung von der <xref:System.Uri> Klassenkonstruktor akzeptiert einen Parameter vom Typ <xref:System.UriKind> können Sie angeben, ob ein Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ist absolut oder relativ.</span><span class="sxs-lookup"><span data-stu-id="00806-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is either absolute or relative.</span></span>  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 <span data-ttu-id="00806-252">Sie sollten nur angeben <xref:System.UriKind.Absolute> oder <xref:System.UriKind.Relative> Wenn sind Sie sicher, dass das angegebene Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] kann einen oder anderen.</span><span class="sxs-lookup"><span data-stu-id="00806-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is one or the other.</span></span> <span data-ttu-id="00806-253">Wenn Sie nicht, dass den Typ des Packs wissen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verwendet wird, z. B. wenn ein Benutzer einen Paket- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] zur Laufzeit verwenden <xref:System.UriKind.RelativeOrAbsolute> stattdessen.</span><span class="sxs-lookup"><span data-stu-id="00806-253">If you don't know the type of pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is used, such as when a user enters a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 <span data-ttu-id="00806-254">Tabelle 3 sehen Sie die verschiedenen relative Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , die Sie im Code angeben können, mithilfe von <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00806-254">Table 3 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="00806-255">Tabelle 3: Absolute Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="00806-255">Table 3: Absolute Pack URIs in Code</span></span>  
  
|<span data-ttu-id="00806-256">Datei</span><span class="sxs-lookup"><span data-stu-id="00806-256">File</span></span>|<span data-ttu-id="00806-257">Absolute Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00806-257">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="00806-258">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-259">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-260">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-261">Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-262">Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-263">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="00806-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-264">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-265">Datei der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="00806-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="00806-266">Datei der Ursprungssite im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 <span data-ttu-id="00806-267">Tabelle 4 sehen Sie die verschiedenen relative Paket- [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] , die Sie angeben können, in Code mit <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00806-267">Table 4 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="00806-268">Tabelle 4: Relative Paket-URIs im Code</span><span class="sxs-lookup"><span data-stu-id="00806-268">Table 4: Relative Pack URIs in Code</span></span>  
  
|<span data-ttu-id="00806-269">Datei</span><span class="sxs-lookup"><span data-stu-id="00806-269">File</span></span>|<span data-ttu-id="00806-270">Relative Paket [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00806-270">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="00806-271">Ressourcendatei – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="00806-272">Ressourcendatei im Unterordner – lokale Assembly</span><span class="sxs-lookup"><span data-stu-id="00806-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="00806-273">Ressourcendatei – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="00806-274">Ressourcendatei im Unterordner – Assembly, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="00806-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="00806-275">Inhaltsdatei</span><span class="sxs-lookup"><span data-stu-id="00806-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="00806-276">Inhaltsdatei im Unterordner</span><span class="sxs-lookup"><span data-stu-id="00806-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="00806-277">Häufige Szenarien mit Paket-URIs</span><span class="sxs-lookup"><span data-stu-id="00806-277">Common Pack URI Scenarios</span></span>  
 <span data-ttu-id="00806-278">In den vorherigen Abschnitten wurde erläutert, wie Sie Paket-erstellen [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Ressource, Inhalte und Dateien der Ursprungssite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="00806-278">The preceding sections have discussed how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="00806-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], werden diese Konstruktionen auf vielfältige Weise verwendet und den folgenden Abschnitten werden einige allgemeine Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="00806-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="00806-280">Angeben der Benutzeroberfläche, die beim Starten einer Anwendung angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="00806-280">Specifying the UI to Show When an Application Starts</span></span>  
 <span data-ttu-id="00806-281"><xref:System.Windows.Application.StartupUri%2A> Gibt das erste [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] beim Anzeigen einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="00806-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="00806-282">Bei eigenständigen Anwendungen kann die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] können ein Fenster sein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00806-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 <span data-ttu-id="00806-283">Eigenständige Anwendungen und [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] können auch als erste Benutzeroberfläche, eine Seite angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00806-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 <span data-ttu-id="00806-284">Wenn die Anwendung eine eigenständige Anwendung ist und eine Seite wird angegeben, mit <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] öffnet eine <xref:System.Windows.Navigation.NavigationWindow> auf die Seite zu hosten.</span><span class="sxs-lookup"><span data-stu-id="00806-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="00806-285">Für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], wird die Seite im Hostbrowser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00806-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a><span data-ttu-id="00806-286">Navigieren zu einer Seite</span><span class="sxs-lookup"><span data-stu-id="00806-286">Navigating to a Page</span></span>  
 <span data-ttu-id="00806-287">Im folgenden Beispiel wird das Navigieren zu einer Seite veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="00806-287">The following example shows how to navigate to a page.</span></span>  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 <span data-ttu-id="00806-288">Weitere Informationen zu den verschiedenen Möglichkeiten zum Navigieren in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], finden Sie unter [Übersicht über die Navigation](navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="00806-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](navigation-overview.md).</span></span>  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a><span data-ttu-id="00806-289">Angeben eines Fenstersymbols</span><span class="sxs-lookup"><span data-stu-id="00806-289">Specifying a Window Icon</span></span>  
 <span data-ttu-id="00806-290">Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines URIs das Symbol eines Fensters angeben.</span><span class="sxs-lookup"><span data-stu-id="00806-290">The following example shows how to use a URI to specify a window's icon.</span></span>  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 <span data-ttu-id="00806-291">Weitere Informationen finden Sie unter <xref:System.Windows.Window.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="00806-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="00806-292">Laden von Bild-, Audio- und Videodateien</span><span class="sxs-lookup"><span data-stu-id="00806-292">Loading Image, Audio, and Video Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="00806-293">ermöglicht es Anwendungen, die alle identifiziert und Pack geladen werden können, verwenden Sie eine Vielzahl von Medientypen, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00806-293">allows applications to use a wide variety of media types, all of which can be identified and loaded with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], as shown in the following examples.</span></span>  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 <span data-ttu-id="00806-294">Weitere Informationen zum Arbeiten mit Medieninhalten finden Sie unter [Grafiken und Multimedia](../graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="00806-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="00806-295">Laden eines Ressourcenverzeichnisses von der Ursprungssite</span><span class="sxs-lookup"><span data-stu-id="00806-295">Loading a Resource Dictionary from the Site of Origin</span></span>  
 <span data-ttu-id="00806-296">Ressourcenverzeichnisse (<xref:System.Windows.ResourceDictionary>) kann verwendet werden, um Anwendungsdesigns zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="00806-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="00806-297">Eine Möglichkeit, Designs zu erstellen und zu verwalten, besteht darin, mehrere Designs als Ressourcenverzeichnisse zu erstellen, die auf der Ursprungssite einer Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="00806-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="00806-298">Dadurch können Designs hinzugefügt und aktualisiert werden, ohne dass eine Anwendung erneut kompiliert und bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="00806-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="00806-299">Die Ressourcenverzeichnisse können identifiziert und geladen werden mit Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die im folgenden Beispiel dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="00806-299">These resource dictionaries can be identified and loaded using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], which is shown in the following example.</span></span>  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 <span data-ttu-id="00806-300">Eine Übersicht über Designs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], finden Sie unter [Stile und Vorlagen](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="00806-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00806-301">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00806-301">See also</span></span>

- [<span data-ttu-id="00806-302">WPF-Anwendungsressource, Inhalts- und Datendateien</span><span class="sxs-lookup"><span data-stu-id="00806-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
