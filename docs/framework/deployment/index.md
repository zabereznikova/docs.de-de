---
title: Bereitstellen von .NET Framework und Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2686d0db966192606656167d6e505f34ded333f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="3b081-102">Bereitstellen von .NET Framework und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3b081-102">Deploying the .NET Framework and Applications</span></span>
<span data-ttu-id="3b081-103">Dieser Artikel hilft Ihnen dabei, mit der Bereitstellung des .NET Framework mit Ihrer Anwendung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="3b081-103">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="3b081-104">Die meisten der Informationen sind für Entwickler, OEM- und Organisationsadministratoren vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3b081-104">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="3b081-105">Benutzer, die .NET Framework auf ihren Computern installieren möchten, sollten die Informationen unter [Installieren von .NET Framework](~/docs/framework/install/index.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="3b081-105">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](~/docs/framework/install/index.md).</span></span>  
  
## <a name="key-deployment-resources"></a><span data-ttu-id="3b081-106">Wichtige Bereitstellungsressourcen</span><span class="sxs-lookup"><span data-stu-id="3b081-106">Key Deployment Resources</span></span>  
 <span data-ttu-id="3b081-107">Verwenden Sie die folgenden Links zu anderen MSDN-Themen, um genaue Informationen zum Bereitstellen und Warten von .NET Framework zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3b081-107">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>  
  
 <span data-ttu-id="3b081-108">**Setup und Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="3b081-108">**Setup and deployment**</span></span>  
  
-   <span data-ttu-id="3b081-109">Allgemeine Informationen zum Installer und der Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="3b081-109">General installer and deployment information:</span></span>  
  
    -   <span data-ttu-id="3b081-110">Installeroptionen:</span><span class="sxs-lookup"><span data-stu-id="3b081-110">Installer options:</span></span>  
  
        -   [<span data-ttu-id="3b081-111">Webinstaller</span><span class="sxs-lookup"><span data-stu-id="3b081-111">Web installer</span></span>](~/docs/framework/install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)  
  
        -   [<span data-ttu-id="3b081-112">Offline-Installer</span><span class="sxs-lookup"><span data-stu-id="3b081-112">Offline installer</span></span>](~/docs/framework/install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)  
  
    -   <span data-ttu-id="3b081-113">Installationsmodi:</span><span class="sxs-lookup"><span data-stu-id="3b081-113">Installation modes:</span></span>  
  
        -   [<span data-ttu-id="3b081-114">Automatische Installation</span><span class="sxs-lookup"><span data-stu-id="3b081-114">Silent installation</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining_custom)  
  
        -   [<span data-ttu-id="3b081-115">Anzeigen einer Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="3b081-115">Displaying a UI</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining_default)  
  
    -   [<span data-ttu-id="3b081-116">Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen</span><span class="sxs-lookup"><span data-stu-id="3b081-116">Reducing system restarts during .NET Framework 4.5 installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
  
    -   [<span data-ttu-id="3b081-117">Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3b081-117">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](~/docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)  
  
-   <span data-ttu-id="3b081-118">Bereitstellen von .NET Framework mit einer Clientanwendung (für Entwickler):</span><span class="sxs-lookup"><span data-stu-id="3b081-118">Deploying the .NET Framework with a client application (for developers):</span></span>  
  
    -   <span data-ttu-id="3b081-119">[Verwenden von InstallShield](../../../docs/framework/deployment/deployment-guide-for-developers.md#installshield-deployment) in einem Setup- und Bereitstellungsprojekt</span><span class="sxs-lookup"><span data-stu-id="3b081-119">[Using InstallShield](../../../docs/framework/deployment/deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>  
  
    -   [<span data-ttu-id="3b081-120">Verwenden einer Visual Studio-ClickOnce-Anwendung</span><span class="sxs-lookup"><span data-stu-id="3b081-120">Using a Visual Studio ClickOnce application</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#clickonce-deployment)  
  
    -   [<span data-ttu-id="3b081-121">Erstellen eines WiX-Installationspakets</span><span class="sxs-lookup"><span data-stu-id="3b081-121">Creating a WiX installation package</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#wix)  
  
    -   [<span data-ttu-id="3b081-122">Verwenden eines benutzerdefinierten Installers</span><span class="sxs-lookup"><span data-stu-id="3b081-122">Using a custom installer</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining)  
  
    -   <span data-ttu-id="3b081-123">[Zusätzliche Informationen](../../../docs/framework/deployment/deployment-guide-for-developers.md) für Entwickler</span><span class="sxs-lookup"><span data-stu-id="3b081-123">[Additional information](../../../docs/framework/deployment/deployment-guide-for-developers.md) for developers</span></span>  
  
-   <span data-ttu-id="3b081-124">Bereitstellen von .NET Framework (für OEMs und Administratoren):</span><span class="sxs-lookup"><span data-stu-id="3b081-124">Deploying the .NET Framework (for OEMs and administrators):</span></span>  
  
    -   [<span data-ttu-id="3b081-125">Windows Assessment and Deployment Kit (ADK)</span><span class="sxs-lookup"><span data-stu-id="3b081-125">Windows Assessment and Deployment Kit (ADK)</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=254976)  
  
    -   [<span data-ttu-id="3b081-126">Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="3b081-126">Administrator's guide</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
  
 <span data-ttu-id="3b081-127">**Wartung**</span><span class="sxs-lookup"><span data-stu-id="3b081-127">**Servicing**</span></span>  
  
-   <span data-ttu-id="3b081-128">Allgemeine Informationen finden Sie im [.NET Framework-Blog](http://go.microsoft.com/fwlink/p/?LinkId=254977).</span><span class="sxs-lookup"><span data-stu-id="3b081-128">For general information, see the [.NET Framework blog](http://go.microsoft.com/fwlink/p/?LinkId=254977)</span></span>  
  
-   [<span data-ttu-id="3b081-129">Erkennen von Versionen</span><span class="sxs-lookup"><span data-stu-id="3b081-129">Detecting versions</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
  
-   [<span data-ttu-id="3b081-130">Erkennen von Service Packs und Updates</span><span class="sxs-lookup"><span data-stu-id="3b081-130">Detecting service packs and updates</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
  
## <a name="features-that-simplify-deployment"></a><span data-ttu-id="3b081-131">Funktionen, die die Bereitstellung vereinfachen</span><span class="sxs-lookup"><span data-stu-id="3b081-131">Features That Simplify Deployment</span></span>  
 <span data-ttu-id="3b081-132">.NET Framework stellt zahlreiche Grundfunktionen bereit, die die Bereitstellung Ihrer Anwendungen vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="3b081-132">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>  
  
-   <span data-ttu-id="3b081-133">Anwendungen ohne unerwünschte Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="3b081-133">No-impact applications.</span></span>  
  
     <span data-ttu-id="3b081-134">Diese Funktion bietet Anwendungsisolierung und beseitigt DLL-Konflikte.</span><span class="sxs-lookup"><span data-stu-id="3b081-134">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="3b081-135">Komponenten haben standardmäßig keinen Einfluss auf andere Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3b081-135">By default, components do not affect other applications.</span></span>  
  
-   <span data-ttu-id="3b081-136">Private Komponenten (durch standardmäßige Voreinstellung).</span><span class="sxs-lookup"><span data-stu-id="3b081-136">Private components by default.</span></span>  
  
     <span data-ttu-id="3b081-137">Komponenten werden standardmäßig im Anwendungsverzeichnis bereitgestellt und sind nur innerhalb der dort enthaltenen Anwendung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="3b081-137">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>  
  
-   <span data-ttu-id="3b081-138">Kontrollierte, gemeinsame Verwendung von Code.</span><span class="sxs-lookup"><span data-stu-id="3b081-138">Controlled code sharing.</span></span>  
  
     <span data-ttu-id="3b081-139">Im Fall gemeinsamer Verwendung von Code müssen Sie Code explizit zur gemeinsamen Verwendung bereitstellen. Dies sollte kein Standardverhalten sein.</span><span class="sxs-lookup"><span data-stu-id="3b081-139">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>  
  
-   <span data-ttu-id="3b081-140">Paralleles Versioning.</span><span class="sxs-lookup"><span data-stu-id="3b081-140">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="3b081-141">Mehrere Versionen einer Komponente oder einer Anwendung können gleichzeitig vorhanden sein. Sie können wählen, welche Versionen Sie verwenden möchten. Durch die Common Language Runtime werden Versionsrichtlinien erzwungen.</span><span class="sxs-lookup"><span data-stu-id="3b081-141">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>  
  
-   <span data-ttu-id="3b081-142">Bereitstellung und Replikation durch XCOPY.</span><span class="sxs-lookup"><span data-stu-id="3b081-142">XCOPY deployment and replication.</span></span>  
  
     <span data-ttu-id="3b081-143">Selbstbeschreibende und unabhängige Komponenten und Anwendungen können ohne Registrierungseinträge oder Abhängigkeiten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3b081-143">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>  
  
-   <span data-ttu-id="3b081-144">Dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="3b081-144">On-the-fly updates.</span></span>  
  
     <span data-ttu-id="3b081-145">Administratoren können Hosts wie z. B. ASP.NET verwenden, um DLLs von Programmen auch auf Remotecomputern zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3b081-145">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>  
  
-   <span data-ttu-id="3b081-146">Integration in Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="3b081-146">Integration with the Windows Installer.</span></span>  
  
     <span data-ttu-id="3b081-147">Für die Bereitstellung Ihrer Anwendung stehen Funktionen wie Werbung, Veröffentlichung, Reparatur und Installation bei Bedarf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3b081-147">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>  
  
-   <span data-ttu-id="3b081-148">Enterprise-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3b081-148">Enterprise deployment.</span></span>  
  
     <span data-ttu-id="3b081-149">Diese Funktion macht die einfache Verteilung von Software, einschließlich der Verwendung von Active Directory, möglich.</span><span class="sxs-lookup"><span data-stu-id="3b081-149">This feature provides easy software distribution, including using Active Directory.</span></span>  
  
-   <span data-ttu-id="3b081-150">Herunterladen und Zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="3b081-150">Downloading and caching.</span></span>  
  
     <span data-ttu-id="3b081-151">Durch inkrementelles Herunterladen werden Downloads klein gehalten. Komponenten können isoliert werden und somit nur für eine Anwendung verfügbar sein und mit minimalen Auswirkungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3b081-151">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>  
  
-   <span data-ttu-id="3b081-152">Teilweise vertrauenswürdiger Code.</span><span class="sxs-lookup"><span data-stu-id="3b081-152">Partially trusted code.</span></span>  
  
     <span data-ttu-id="3b081-153">Die Identität basiert auf dem Code, nicht auf dem Benutzer. Zertifikatdialogfelder werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b081-153">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>  
  
## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="3b081-154">Verpacken und Verteilen von .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3b081-154">Packaging and Distributing .NET Framework Applications</span></span>  
 <span data-ttu-id="3b081-155">Einige Informationen über das Packen und Bereitstellen in .NET Framework erhalten Sie in anderen Abschnitten der Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="3b081-155">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="3b081-156">Diese Abschnitte enthalten Informationen zu den selbstbeschreibenden Einheiten mit dem Namen [Assemblys](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md), die keine Registrierungseinträge benötigen, zu [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md), die die Eindeutigkeit der Namen gewährleisten und das Vortäuschen von Namen verhindern, sowie zu [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md), die viele der in Zusammenhang mit DLL-Konflikten auftretenden Probleme behandeln.</span><span class="sxs-lookup"><span data-stu-id="3b081-156">Those sections provide information about the self-describing units called [assemblies](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md), which require no registry entries, [strong-named assemblies](../../../docs/framework/app-domains/strong-named-assemblies.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../../docs/framework/app-domains/assembly-versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="3b081-157">In den folgenden Abschnitten finden Sie Informationen zum Verpacken und Verteilen von .NET Framework-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3b081-157">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>  
  
### <a name="packaging"></a><span data-ttu-id="3b081-158">Verpacken</span><span class="sxs-lookup"><span data-stu-id="3b081-158">Packaging</span></span>  
 <span data-ttu-id="3b081-159">In .NET Framework werden die folgenden Optionen für das Verpacken von Anwendungen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="3b081-159">The .NET Framework provides the following options for packaging applications:</span></span>  
  
-   <span data-ttu-id="3b081-160">Als einzelne Assembly oder als Auflistung von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3b081-160">As a single assembly or as a collection of assemblies.</span></span>  
  
     <span data-ttu-id="3b081-161">Bei dieser Option verwenden Sie einfach die DLL- oder EXE-Dateien so, wie sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3b081-161">With this option, you simply use the .dll or .exe files as they were built.</span></span>  
  
-   <span data-ttu-id="3b081-162">Als CAB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="3b081-162">As cabinet (CAB) files.</span></span>  
  
     <span data-ttu-id="3b081-163">Mit dieser Option komprimieren Sie Dateien in CAB-Dateien, damit die Verteilung oder der Download weniger zeitaufwendig ist.</span><span class="sxs-lookup"><span data-stu-id="3b081-163">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>  
  
-   <span data-ttu-id="3b081-164">Als Windows Installer-Paket oder in anderen Installer-Formaten.</span><span class="sxs-lookup"><span data-stu-id="3b081-164">As a Windows Installer package or in other installer formats.</span></span>  
  
     <span data-ttu-id="3b081-165">Mit dieser Option erstellen Sie MSI-Dateien zur Verwendung mit dem Windows Installer. Bei Verwendung eines anderen Installers verpacken Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3b081-165">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>  
  
### <a name="distribution"></a><span data-ttu-id="3b081-166">Verteilung</span><span class="sxs-lookup"><span data-stu-id="3b081-166">Distribution</span></span>  
 <span data-ttu-id="3b081-167">In .NET Framework werden die folgenden Optionen für das Verteilen von Anwendungen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="3b081-167">The .NET Framework provides the following options for distributing applications:</span></span>  
  
-   <span data-ttu-id="3b081-168">Verwenden von XCOPY oder FTP.</span><span class="sxs-lookup"><span data-stu-id="3b081-168">Use XCOPY or FTP.</span></span>  
  
     <span data-ttu-id="3b081-169">Da Common Language Runtime-Anwendungen selbstbeschreibend sind und keine Registrierungseinträge erfordern, können Sie XCOPY oder FTP verwenden, um die Anwendung einfach in ein entsprechendes Verzeichnis zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="3b081-169">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="3b081-170">Die Anwendung kann dann von diesem Verzeichnis aus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3b081-170">The application can then be run from that directory.</span></span>  
  
-   <span data-ttu-id="3b081-171">Herunterladen von Code.</span><span class="sxs-lookup"><span data-stu-id="3b081-171">Use code download.</span></span>  
  
     <span data-ttu-id="3b081-172">Wenn Sie die Anwendung über das Internet oder ein Firmenintranet vertreiben, laden Sie den Code einfach auf einen Computer herunter und führen die Anwendung dort aus.</span><span class="sxs-lookup"><span data-stu-id="3b081-172">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>  
  
-   <span data-ttu-id="3b081-173">Verwenden eines Installationsprogramms wie z. B. Windows Installer 2.0.</span><span class="sxs-lookup"><span data-stu-id="3b081-173">Use an installer program such as Windows Installer 2.0.</span></span>  
  
     <span data-ttu-id="3b081-174">Windows Installer 2.0 kann Assemblys von .NET Framework im globalen Assemblycache und in privaten Verzeichnissen installieren, reparieren oder daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="3b081-174">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>  
  
### <a name="installation-location"></a><span data-ttu-id="3b081-175">Installationsspeicherort</span><span class="sxs-lookup"><span data-stu-id="3b081-175">Installation Location</span></span>  
 <span data-ttu-id="3b081-176">Informationen zur Bereitstellung der Anwendungsassemblys für die Laufzeit finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3b081-176">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="3b081-177">Sicherheitsüberlegungen können bei der Bereitstellung einer Anwendung ebenfalls eine Rolle spielen.</span><span class="sxs-lookup"><span data-stu-id="3b081-177">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="3b081-178">Sicherheitsberechtigungen werden verwaltetem Code in Abhängigkeit von der Position gewährt.</span><span class="sxs-lookup"><span data-stu-id="3b081-178">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="3b081-179">Das Bereitstellen von Anwendungen oder Komponenten an Speicherorten mit geringer Vertrauenswürdigkeit, z. B. im Internet, schränkt die Möglichkeiten hinsichtlich einer Anwendung oder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="3b081-179">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="3b081-180">Weitere Informationen zu Bereitstellungs- und Sicherheitsüberlegungen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="3b081-180">For more information about deployment and security considerations, see [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="3b081-181">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3b081-181">Related Topics</span></span>  
  
|<span data-ttu-id="3b081-182">Titel</span><span class="sxs-lookup"><span data-stu-id="3b081-182">Title</span></span>|<span data-ttu-id="3b081-183">description</span><span class="sxs-lookup"><span data-stu-id="3b081-183">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3b081-184">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="3b081-184">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|<span data-ttu-id="3b081-185">Beschreibt, wie die Common Language Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b081-185">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|  
|[<span data-ttu-id="3b081-186">Bewährte Methoden für das Laden von Assemblys</span><span class="sxs-lookup"><span data-stu-id="3b081-186">Best Practices for Assembly Loading</span></span>](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)|<span data-ttu-id="3b081-187">In diesem Artikel werden Möglichkeiten zur Vermeidung von Problemen mit der Typidentität erläutert, die zu <xref:System.InvalidCastException>, <xref:System.MissingMethodException> und anderen Fehlern führen können.</span><span class="sxs-lookup"><span data-stu-id="3b081-187">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|  
|[<span data-ttu-id="3b081-188">Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen</span><span class="sxs-lookup"><span data-stu-id="3b081-188">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)|<span data-ttu-id="3b081-189">Beschreibt den Neustart-Manager, der Neustarts nach Möglichkeit verhindert, und erläutert, wie Anwendungen, mit denen .NET Framework installiert wird, den Neustart-Manager nutzen können.</span><span class="sxs-lookup"><span data-stu-id="3b081-189">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|  
|[<span data-ttu-id="3b081-190">Bereitstellungshandbuch für Administratoren</span><span class="sxs-lookup"><span data-stu-id="3b081-190">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)|<span data-ttu-id="3b081-191">Hierin wird erläutert, wie ein Systemadministrator mit System Center Configuration Manager (SCCM) .NET Framework und dessen Systemabhängigkeiten in einem Netzwerk bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="3b081-191">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>|  
|[<span data-ttu-id="3b081-192">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="3b081-192">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)|<span data-ttu-id="3b081-193">Es wird erklärt, wie Entwickler .NET Framework auf den Computern der Benutzer mit ihren Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="3b081-193">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|  
|[<span data-ttu-id="3b081-194">Bereitstellen von Anwendungen, Diensten und Komponenten</span><span class="sxs-lookup"><span data-stu-id="3b081-194">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="3b081-195">Erläutert Bereitstellungsoptionen in Visual Studio, einschließlich Anweisungen zum Veröffentlichen einer Anwendung mit ClickOnce- und Windows Installer-Technologie.</span><span class="sxs-lookup"><span data-stu-id="3b081-195">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>| 
|[<span data-ttu-id="3b081-196">Veröffentlichen von ClickOnce-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3b081-196">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="3b081-197">Beschreibt, wie eine Windows Forms-Anwendung verpackt und mit ClickOnce auf Clientcomputern in einem Netzwerk bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b081-197">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|  
|[<span data-ttu-id="3b081-198">Verpacken und Bereitstellen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3b081-198">Packaging and Deploying Resources</span></span>](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="3b081-199">Beschreibt das sternenförmige Modell von .NET Framework zum Verpacken und Bereitstellen von Ressourcen und enthält Informationen zu Namenskonventionen für Ressourcen, Fallbackprozessen und Verpackungsalternativen.</span><span class="sxs-lookup"><span data-stu-id="3b081-199">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|  
|[<span data-ttu-id="3b081-200">Bereitstellen einer Interop-Anwendung</span><span class="sxs-lookup"><span data-stu-id="3b081-200">Deploying an Interop Application</span></span>](../../../docs/framework/interop/deploying-an-interop-application.md)|<span data-ttu-id="3b081-201">Erläutert, wie Interop-Anwendungen verteilt und installiert werden, die üblicherweise eine .NET Framework-Clientassembly enthalten. Außerdem wird beschrieben, wie Interopassemblys, die unterschiedliche COM-Typbibliotheken darstellen, sowie registrierte COM-Komponenten verteilt und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="3b081-201">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|  
|[<span data-ttu-id="3b081-202">Gewusst wie: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3b081-202">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="3b081-203">Beschreibt, wie der .NET Framework-Setupvorgang automatisch gestartet und nachverfolgt und dabei eine eigene Ansicht des Setupstatus angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b081-203">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b081-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b081-204">See Also</span></span>  
 [<span data-ttu-id="3b081-205">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="3b081-205">Development Guide</span></span>](../../../docs/framework/development-guide.md)
