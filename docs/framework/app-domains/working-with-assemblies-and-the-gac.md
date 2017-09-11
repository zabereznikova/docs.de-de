---
title: Arbeiten mit Assemblys und dem globalen Assemblychache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0c656cbad746e044a6dbf187ce86fd4738d6ef98
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="57937-102">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="57937-102">Working with Assemblies and the Global Assembly Cache</span></span>
<span data-ttu-id="57937-103">Wenn Sie eine Assembly freigeben und für mehrere Anwendungen gemeinsam nutzen möchten, können Sie die Assembly im globalen Assemblycache installieren.</span><span class="sxs-lookup"><span data-stu-id="57937-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="57937-104">Jeder Computer, auf dem die Common Language Runtime installiert ist, verfügt über diesen computerweiten Codecache.</span><span class="sxs-lookup"><span data-stu-id="57937-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="57937-105">Im globalen Assemblycache werden Assemblys gespeichert, die speziell für die gemeinsame Verwendung durch mehrere Anwendungen auf dem Computer vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="57937-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="57937-106">Eine Assembly muss einen starken Namen haben, um im globalen Assemblycache installiert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="57937-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57937-107">Bei Assemblys, die im globalen Assemblycache abgelegt werden, müssen Assembly- und Dateiname (ohne die Dateinamenerweiterung) übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="57937-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="57937-108">Beispielsweise muss der Dateiname einer Assembly, die den Namen myAssembly hat, entweder myAssembly.exe oder myAssembly.dll lauten.</span><span class="sxs-lookup"><span data-stu-id="57937-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
 <span data-ttu-id="57937-109">Geben Sie Assemblys nur dann durch eine Installation im globalen Assemblycache frei, wenn dies unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="57937-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="57937-110">Wenn die Freigabe einer Assembly nicht unbedingt erforderlich ist, empfiehlt es sich, die Assemblyabhängigkeiten privat zu halten und Assemblys im Anwendungsverzeichnis abzulegen.</span><span class="sxs-lookup"><span data-stu-id="57937-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="57937-111">Assemblys müssen außerdem nicht im globalen Assemblycache installiert sein, um für COM-Interop oder nicht verwalteten Code verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="57937-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
 <span data-ttu-id="57937-112">Es gibt verschiedene Gründe, eine Assembly im globalen Assemblycache zu installieren:</span><span class="sxs-lookup"><span data-stu-id="57937-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="57937-113">Freigegebener Standort.</span><span class="sxs-lookup"><span data-stu-id="57937-113">Shared location.</span></span>  
  
     <span data-ttu-id="57937-114">Assemblys, die für die Verwendung durch Anwendungen vorgesehen sind, können im globalen Assemblycache installiert werden.</span><span class="sxs-lookup"><span data-stu-id="57937-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="57937-115">Wenn beispielsweise alle Anwendungen eine im globalen Assemblycache befindliche Assembly verwenden sollen, kann der Datei Machine.config eine Versionsrichtlinienanweisung hinzugefügt werden, die Verweise auf die Assembly umleitet.</span><span class="sxs-lookup"><span data-stu-id="57937-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
-   <span data-ttu-id="57937-116">Dateisicherheit.</span><span class="sxs-lookup"><span data-stu-id="57937-116">File security.</span></span>  
  
     <span data-ttu-id="57937-117">Administratoren verwenden zum Schutz des Verzeichnisses systemroot oft eine Zugriffssteuerungsliste (ACL, Access Control List), um Schreib- und Ausführungszugriffe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="57937-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="57937-118">Da der globale Assemblycache im Verzeichnis systemroot installiert ist, erbt er die ACL dieses Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="57937-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="57937-119">Aus diesem Grund empfiehlt es sich, nur Benutzern mit Administratorrechten das Löschen von Dateien aus dem globalen Assemblycache zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="57937-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
-   <span data-ttu-id="57937-120">Paralleles Versioning.</span><span class="sxs-lookup"><span data-stu-id="57937-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="57937-121">Im globalen Assemblycache dürfen sich mehrere Assemblys mit demselben Namen befinden, solange sich ihre Versionsinformationen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="57937-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="57937-122">Zusätzliche Suchposition.</span><span class="sxs-lookup"><span data-stu-id="57937-122">Additional search location.</span></span>  
  
     <span data-ttu-id="57937-123">Die Common Language Runtime durchsucht den globalen Assemblycache nach der angeforderten Assembly, bevor CodeBase-Informationen in einer Konfigurationsdatei überprüft oder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57937-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="57937-124">Beachten Sie, dass es Szenarien gibt, in denen eine Assembly ausdrücklich nicht im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="57937-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="57937-125">Wenn Sie eine der Assemblys, aus denen eine Anwendung besteht, im globalen Assemblycache ablegen, können Sie die Anwendung anschließend weder replizieren noch installieren, indem Sie mit XCOPY das Anwendungsverzeichnis kopieren.</span><span class="sxs-lookup"><span data-stu-id="57937-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="57937-126">In einem solchen Fall müssen Sie die Assembly ebenfalls im globalen Assemblycache ablegen.</span><span class="sxs-lookup"><span data-stu-id="57937-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57937-127">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="57937-127">In This Section</span></span>  
 [<span data-ttu-id="57937-128">Gewusst wie: Installieren einer Assembly in den globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="57937-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 <span data-ttu-id="57937-129">Beschreibt die Möglichkeiten, eine Assembly im globalen Assemblycache zu installieren.</span><span class="sxs-lookup"><span data-stu-id="57937-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
 [<span data-ttu-id="57937-130">Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches</span><span class="sxs-lookup"><span data-stu-id="57937-130">How to: View the Contents of the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 <span data-ttu-id="57937-131">Verwenden Sie das [Global Assembly Cache-Tool („gacutil.exe“)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="57937-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="57937-132">Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="57937-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 <span data-ttu-id="57937-133">Verwenden Sie das [Global Assembly Cache-Tool („gacutil.exe“)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um eine Assembly aus dem globalen Assemblycache zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="57937-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
 [<span data-ttu-id="57937-134">Verwenden von Serviced Components mit dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="57937-134">Using Serviced Components with the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 <span data-ttu-id="57937-135">Erläutert, warum Serviced Components (verwaltete COM+-Komponenten) im globalen Assemblycache abgelegt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="57937-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="57937-136">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="57937-136">Related Sections</span></span>  
 [<span data-ttu-id="57937-137">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="57937-137">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="57937-138">Bietet eine Übersicht über das Erstellen von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="57937-138">Provides an overview of creating assemblies.</span></span>  
  
 [<span data-ttu-id="57937-139">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="57937-139">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 <span data-ttu-id="57937-140">Beschreibt den globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="57937-140">Describes the global assembly cache.</span></span>  
  
 [<span data-ttu-id="57937-141">Gewusst wie: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="57937-141">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="57937-142">Erläutert, wie der [IL-Disassembler („ildasm.exe“)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwendet wird, um Microsoft Intermediate Language-Informationen (MSIL) in einer Assembly anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="57937-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
 [<span data-ttu-id="57937-143">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="57937-143">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="57937-144">Beschreibt, wie die Assemblys, die die Anwendung bilden, von der Common Language Runtime gesucht und geladen werden.</span><span class="sxs-lookup"><span data-stu-id="57937-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
 [<span data-ttu-id="57937-145">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="57937-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="57937-146">Beschreibt Assemblys, die die Bausteine verwalteter Anwendungen bilden.</span><span class="sxs-lookup"><span data-stu-id="57937-146">Describes assemblies, the building blocks of managed applications.</span></span>

