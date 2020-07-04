---
title: Bereitstellen von .NET Framework und Anwendungen
description: Erste Schritte beim Bereitstellen von .NET mit Ihrer Anwendung. .NET bietet Anwendungen ohne Auswirkungen, standardmäßig private Komponenten, kontrollierte Codefreigabe und vieles mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: cce888c962c9ab83c13cce4040eb9ba50270972d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803500"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="33d69-104">Bereitstellen von .NET Framework und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="33d69-104">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="33d69-105">Dieser Artikel hilft Ihnen dabei, mit der Bereitstellung des .NET Framework mit Ihrer Anwendung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="33d69-105">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="33d69-106">Die meisten der Informationen sind für Entwickler, OEM- und Organisationsadministratoren vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="33d69-106">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="33d69-107">Benutzer, die .NET Framework auf ihren Computern installieren möchten, sollten die Informationen unter [Installieren von .NET Framework](../install/index.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="33d69-107">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="33d69-108">Wichtige Bereitstellungsressourcen</span><span class="sxs-lookup"><span data-stu-id="33d69-108">Key Deployment Resources</span></span>

<span data-ttu-id="33d69-109">Verwenden Sie die folgenden Links zu anderen MSDN-Themen, um genaue Informationen zum Bereitstellen und Warten von .NET Framework zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="33d69-109">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="33d69-110">**Setup und Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="33d69-110">**Setup and deployment**</span></span>

- <span data-ttu-id="33d69-111">Allgemeine Informationen zum Installer und der Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="33d69-111">General installer and deployment information:</span></span>

  - <span data-ttu-id="33d69-112">Installeroptionen:</span><span class="sxs-lookup"><span data-stu-id="33d69-112">Installer options:</span></span>

    - [<span data-ttu-id="33d69-113">Webinstaller</span><span class="sxs-lookup"><span data-stu-id="33d69-113">Web installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [<span data-ttu-id="33d69-114">Offline-Installer</span><span class="sxs-lookup"><span data-stu-id="33d69-114">Offline installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - <span data-ttu-id="33d69-115">Installationsmodi:</span><span class="sxs-lookup"><span data-stu-id="33d69-115">Installation modes:</span></span>

    - [<span data-ttu-id="33d69-116">Automatische Installation</span><span class="sxs-lookup"><span data-stu-id="33d69-116">Silent installation</span></span>](deployment-guide-for-developers.md#chaining_custom)

    - [<span data-ttu-id="33d69-117">Anzeigen einer Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="33d69-117">Displaying a UI</span></span>](deployment-guide-for-developers.md#chaining_default)

  - [<span data-ttu-id="33d69-118">Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen</span><span class="sxs-lookup"><span data-stu-id="33d69-118">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="33d69-119">Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33d69-119">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="33d69-120">Bereitstellen von .NET Framework mit einer Clientanwendung (für Entwickler):</span><span class="sxs-lookup"><span data-stu-id="33d69-120">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="33d69-121">[Verwenden von InstallShield](deployment-guide-for-developers.md#installshield-deployment) in einem Setup- und Bereitstellungsprojekt</span><span class="sxs-lookup"><span data-stu-id="33d69-121">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - [<span data-ttu-id="33d69-122">Verwenden einer Visual Studio-ClickOnce-Anwendung</span><span class="sxs-lookup"><span data-stu-id="33d69-122">Using a Visual Studio ClickOnce application</span></span>](deployment-guide-for-developers.md#clickonce-deployment)

  - [<span data-ttu-id="33d69-123">Erstellen eines WiX-Installationspakets</span><span class="sxs-lookup"><span data-stu-id="33d69-123">Creating a WiX installation package</span></span>](deployment-guide-for-developers.md#wix)

  - [<span data-ttu-id="33d69-124">Verwenden eines benutzerdefinierten Installers</span><span class="sxs-lookup"><span data-stu-id="33d69-124">Using a custom installer</span></span>](deployment-guide-for-developers.md#chaining)

  - <span data-ttu-id="33d69-125">[Zusätzliche Informationen](deployment-guide-for-developers.md) für Entwickler</span><span class="sxs-lookup"><span data-stu-id="33d69-125">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="33d69-126">Bereitstellen von .NET Framework (für OEMs und Administratoren):</span><span class="sxs-lookup"><span data-stu-id="33d69-126">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - [<span data-ttu-id="33d69-127">Windows Assessment and Deployment Kit (ADK)</span><span class="sxs-lookup"><span data-stu-id="33d69-127">Windows Assessment and Deployment Kit (ADK)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [<span data-ttu-id="33d69-128">Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="33d69-128">Administrator's guide</span></span>](guide-for-administrators.md)

<span data-ttu-id="33d69-129">**Wartung**</span><span class="sxs-lookup"><span data-stu-id="33d69-129">**Servicing**</span></span>

- <span data-ttu-id="33d69-130">Allgemeine Informationen finden Sie im [.NET Framework-Blog](https://devblogs.microsoft.com/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="33d69-130">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- [<span data-ttu-id="33d69-131">Erkennen von Versionen</span><span class="sxs-lookup"><span data-stu-id="33d69-131">Detecting versions</span></span>](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [<span data-ttu-id="33d69-132">Erkennen von Service Packs und Updates</span><span class="sxs-lookup"><span data-stu-id="33d69-132">Detecting service packs and updates</span></span>](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="33d69-133">Funktionen, die die Bereitstellung vereinfachen</span><span class="sxs-lookup"><span data-stu-id="33d69-133">Features That Simplify Deployment</span></span>

<span data-ttu-id="33d69-134">.NET Framework stellt zahlreiche Grundfunktionen bereit, die die Bereitstellung Ihrer Anwendungen vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="33d69-134">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="33d69-135">Anwendungen ohne unerwünschte Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="33d69-135">No-impact applications.</span></span>

     <span data-ttu-id="33d69-136">Diese Funktion bietet Anwendungsisolierung und beseitigt DLL-Konflikte.</span><span class="sxs-lookup"><span data-stu-id="33d69-136">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="33d69-137">Komponenten haben standardmäßig keinen Einfluss auf andere Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="33d69-137">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="33d69-138">Private Komponenten (durch standardmäßige Voreinstellung).</span><span class="sxs-lookup"><span data-stu-id="33d69-138">Private components by default.</span></span>

     <span data-ttu-id="33d69-139">Komponenten werden standardmäßig im Anwendungsverzeichnis bereitgestellt und sind nur innerhalb der dort enthaltenen Anwendung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="33d69-139">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="33d69-140">Kontrollierte, gemeinsame Verwendung von Code.</span><span class="sxs-lookup"><span data-stu-id="33d69-140">Controlled code sharing.</span></span>

     <span data-ttu-id="33d69-141">Im Fall gemeinsamer Verwendung von Code müssen Sie Code explizit zur gemeinsamen Verwendung bereitstellen. Dies sollte kein Standardverhalten sein.</span><span class="sxs-lookup"><span data-stu-id="33d69-141">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="33d69-142">Paralleles Versioning.</span><span class="sxs-lookup"><span data-stu-id="33d69-142">Side-by-side versioning.</span></span>

     <span data-ttu-id="33d69-143">Mehrere Versionen einer Komponente oder einer Anwendung können gleichzeitig vorhanden sein. Sie können wählen, welche Versionen Sie verwenden möchten. Durch die Common Language Runtime werden Versionsrichtlinien erzwungen.</span><span class="sxs-lookup"><span data-stu-id="33d69-143">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="33d69-144">Bereitstellung und Replikation durch XCOPY.</span><span class="sxs-lookup"><span data-stu-id="33d69-144">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="33d69-145">Selbstbeschreibende und unabhängige Komponenten und Anwendungen können ohne Registrierungseinträge oder Abhängigkeiten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33d69-145">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="33d69-146">Dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="33d69-146">On-the-fly updates.</span></span>

     <span data-ttu-id="33d69-147">Administratoren können Hosts wie z. B. ASP.NET verwenden, um DLLs von Programmen auch auf Remotecomputern zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="33d69-147">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="33d69-148">Integration in Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="33d69-148">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="33d69-149">Für die Bereitstellung Ihrer Anwendung stehen Funktionen wie Werbung, Veröffentlichung, Reparatur und Installation bei Bedarf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="33d69-149">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="33d69-150">Enterprise-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="33d69-150">Enterprise deployment.</span></span>

     <span data-ttu-id="33d69-151">Diese Funktion macht die einfache Verteilung von Software, einschließlich der Verwendung von Active Directory, möglich.</span><span class="sxs-lookup"><span data-stu-id="33d69-151">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="33d69-152">Herunterladen und Zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="33d69-152">Downloading and caching.</span></span>

     <span data-ttu-id="33d69-153">Durch inkrementelles Herunterladen werden Downloads klein gehalten. Komponenten können isoliert werden und somit nur für eine Anwendung verfügbar sein und mit minimalen Auswirkungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33d69-153">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="33d69-154">Teilweise vertrauenswürdiger Code.</span><span class="sxs-lookup"><span data-stu-id="33d69-154">Partially trusted code.</span></span>

     <span data-ttu-id="33d69-155">Die Identität basiert auf dem Code, nicht auf dem Benutzer. Zertifikatdialogfelder werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33d69-155">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="33d69-156">Verpacken und Verteilen von .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="33d69-156">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="33d69-157">Einige Informationen über das Packen und Bereitstellen in .NET Framework erhalten Sie in anderen Abschnitten der Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="33d69-157">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="33d69-158">Diese Abschnitte enthalten Informationen zu den selbstbeschreibenden Einheiten mit dem Namen [Assemblys](../../standard/assembly/index.md), die keine Registrierungseinträge benötigen, zu [Assemblys mit starkem Namen](../../standard/assembly/strong-named.md), die die Eindeutigkeit der Namen gewährleisten und das Vortäuschen von Namen verhindern, sowie zu [Assemblyversionen](../../standard/assembly/versioning.md), die viele der in Zusammenhang mit DLL-Konflikten auftretenden Probleme behandeln.</span><span class="sxs-lookup"><span data-stu-id="33d69-158">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="33d69-159">In den folgenden Abschnitten finden Sie Informationen zum Verpacken und Verteilen von .NET Framework-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="33d69-159">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="33d69-160">Verpacken</span><span class="sxs-lookup"><span data-stu-id="33d69-160">Packaging</span></span>

<span data-ttu-id="33d69-161">In .NET Framework werden die folgenden Optionen für das Verpacken von Anwendungen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="33d69-161">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="33d69-162">Als einzelne Assembly oder als Auflistung von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="33d69-162">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="33d69-163">Bei dieser Option verwenden Sie einfach die DLL- oder EXE-Dateien so, wie sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="33d69-163">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="33d69-164">Als CAB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="33d69-164">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="33d69-165">Mit dieser Option komprimieren Sie Dateien in CAB-Dateien, damit die Verteilung oder der Download weniger zeitaufwendig ist.</span><span class="sxs-lookup"><span data-stu-id="33d69-165">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="33d69-166">Als Windows Installer-Paket oder in anderen Installer-Formaten.</span><span class="sxs-lookup"><span data-stu-id="33d69-166">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="33d69-167">Mit dieser Option erstellen Sie MSI-Dateien zur Verwendung mit dem Windows Installer. Bei Verwendung eines anderen Installers verpacken Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="33d69-167">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="33d69-168">Verteilung</span><span class="sxs-lookup"><span data-stu-id="33d69-168">Distribution</span></span>

<span data-ttu-id="33d69-169">In .NET Framework werden die folgenden Optionen für das Verteilen von Anwendungen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="33d69-169">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="33d69-170">Verwenden von XCOPY oder FTP.</span><span class="sxs-lookup"><span data-stu-id="33d69-170">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="33d69-171">Da Common Language Runtime-Anwendungen selbstbeschreibend sind und keine Registrierungseinträge erfordern, können Sie XCOPY oder FTP verwenden, um die Anwendung einfach in ein entsprechendes Verzeichnis zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="33d69-171">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="33d69-172">Die Anwendung kann dann von diesem Verzeichnis aus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33d69-172">The application can then be run from that directory.</span></span>

- <span data-ttu-id="33d69-173">Herunterladen von Code.</span><span class="sxs-lookup"><span data-stu-id="33d69-173">Use code download.</span></span>

     <span data-ttu-id="33d69-174">Wenn Sie die Anwendung über das Internet oder ein Firmenintranet vertreiben, laden Sie den Code einfach auf einen Computer herunter und führen die Anwendung dort aus.</span><span class="sxs-lookup"><span data-stu-id="33d69-174">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="33d69-175">Verwenden eines Installationsprogramms wie z. B. Windows Installer 2.0.</span><span class="sxs-lookup"><span data-stu-id="33d69-175">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="33d69-176">Windows Installer 2.0 kann Assemblys von .NET Framework im globalen Assemblycache und in privaten Verzeichnissen installieren, reparieren oder daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="33d69-176">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="33d69-177">Installationsspeicherort</span><span class="sxs-lookup"><span data-stu-id="33d69-177">Installation Location</span></span>

<span data-ttu-id="33d69-178">Informationen zur Bereitstellung der Anwendungsassemblys für die Laufzeit finden Sie unter [So sucht Common Language Runtime nach Assemblys](how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="33d69-178">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="33d69-179">Sicherheitsüberlegungen können bei der Bereitstellung einer Anwendung ebenfalls eine Rolle spielen.</span><span class="sxs-lookup"><span data-stu-id="33d69-179">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="33d69-180">Sicherheitsberechtigungen werden verwaltetem Code in Abhängigkeit von der Position gewährt.</span><span class="sxs-lookup"><span data-stu-id="33d69-180">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="33d69-181">Das Bereitstellen von Anwendungen oder Komponenten an Speicherorten mit geringer Vertrauenswürdigkeit, z. B. im Internet, schränkt die Möglichkeiten hinsichtlich einer Anwendung oder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="33d69-181">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="33d69-182">Weitere Informationen zu Bereitstellungs- und Sicherheitsüberlegungen finden Sie unter [Grundlagen der Codezugriffssicherheit](../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="33d69-182">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="33d69-183">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="33d69-183">Related Topics</span></span>

|<span data-ttu-id="33d69-184">Titel</span><span class="sxs-lookup"><span data-stu-id="33d69-184">Title</span></span>|<span data-ttu-id="33d69-185">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33d69-185">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="33d69-186">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="33d69-186">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="33d69-187">Beschreibt, wie die Common Language Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="33d69-187">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="33d69-188">Bewährte Methoden für das Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="33d69-188">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="33d69-189">In diesem Artikel werden Möglichkeiten zur Vermeidung von Problemen mit der Typidentität erläutert, die zu <xref:System.InvalidCastException>, <xref:System.MissingMethodException> und anderen Fehlern führen können.</span><span class="sxs-lookup"><span data-stu-id="33d69-189">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="33d69-190">Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen</span><span class="sxs-lookup"><span data-stu-id="33d69-190">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="33d69-191">Beschreibt den Neustart-Manager, der Neustarts nach Möglichkeit verhindert, und erläutert, wie Anwendungen, mit denen .NET Framework installiert wird, den Neustart-Manager nutzen können.</span><span class="sxs-lookup"><span data-stu-id="33d69-191">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="33d69-192">Bereitstellungshandbuch für Administratoren</span><span class="sxs-lookup"><span data-stu-id="33d69-192">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="33d69-193">Hierin wird erläutert, wie ein Systemadministrator mit Microsoft Endpoint Configuration Manager .NET Framework und dessen Systemabhängigkeiten in einem Netzwerk bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="33d69-193">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="33d69-194">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="33d69-194">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="33d69-195">Es wird erklärt, wie Entwickler .NET Framework auf den Computern der Benutzer mit ihren Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="33d69-195">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="33d69-196">Bereitstellen von Anwendungen, Diensten und Komponenten</span><span class="sxs-lookup"><span data-stu-id="33d69-196">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="33d69-197">Erläutert Bereitstellungsoptionen in Visual Studio, einschließlich Anweisungen zum Veröffentlichen einer Anwendung mit ClickOnce- und Windows Installer-Technologie.</span><span class="sxs-lookup"><span data-stu-id="33d69-197">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="33d69-198">Veröffentlichen von ClickOnce-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="33d69-198">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="33d69-199">Beschreibt, wie eine Windows Forms-Anwendung verpackt und mit ClickOnce auf Clientcomputern in einem Netzwerk bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="33d69-199">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="33d69-200">Verpacken und Bereitstellen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="33d69-200">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="33d69-201">Beschreibt das sternenförmige Modell von .NET Framework zum Verpacken und Bereitstellen von Ressourcen und enthält Informationen zu Namenskonventionen für Ressourcen, Fallbackprozessen und Verpackungsalternativen.</span><span class="sxs-lookup"><span data-stu-id="33d69-201">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="33d69-202">Bereitstellen einer Interop-Anwendung</span><span class="sxs-lookup"><span data-stu-id="33d69-202">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="33d69-203">Erläutert, wie Interop-Anwendungen verteilt und installiert werden, die üblicherweise eine .NET Framework-Clientassembly enthalten. Außerdem wird beschrieben, wie Interopassemblys, die unterschiedliche COM-Typbibliotheken darstellen, sowie registrierte COM-Komponenten verteilt und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="33d69-203">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="33d69-204">How to: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="33d69-204">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="33d69-205">Beschreibt, wie der .NET Framework-Setupvorgang automatisch gestartet und nachverfolgt und dabei eine eigene Ansicht des Setupstatus angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="33d69-205">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="33d69-206">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33d69-206">See also</span></span>

- [<span data-ttu-id="33d69-207">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="33d69-207">Development Guide</span></span>](../development-guide.md)
