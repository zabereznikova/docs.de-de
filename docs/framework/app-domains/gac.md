---
title: Globaler Assemblycache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ca51a06e6e7ec89576facf3a70c789325fd893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="global-assembly-cache"></a><span data-ttu-id="20c24-102">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="20c24-102">Global Assembly Cache</span></span>
<span data-ttu-id="20c24-103">Jeder Computer, auf dem die Common Language Runtime installiert ist, besitzt einen computerweiten Codecache, den so genannten globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="20c24-103">Each computer where the common language runtime is installed has a machine-wide code cache called the global assembly cache.</span></span> <span data-ttu-id="20c24-104">Im globalen Assemblycache werden Assemblys gespeichert, die speziell für die gemeinsame Verwendung durch mehrere Anwendungen auf dem Computer vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="20c24-104">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span>  
  
 <span data-ttu-id="20c24-105">Geben Sie Assemblys nur dann durch eine Installation im globalen Assemblycache frei, wenn dies unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="20c24-105">You should share assemblies by installing them into the global assembly cache only when you need to.</span></span> <span data-ttu-id="20c24-106">Wenn die Freigabe einer Assembly nicht unbedingt erforderlich ist, empfiehlt es sich, die Assemblyabhängigkeiten privat zu halten und Assemblys im Anwendungsverzeichnis abzulegen.</span><span class="sxs-lookup"><span data-stu-id="20c24-106">As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="20c24-107">Assemblys müssen außerdem nicht im globalen Assemblycache installiert sein, um für COM-Interop oder nicht verwalteten Code verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="20c24-107">In addition, it is not necessary to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20c24-108">Es gibt Szenarien, in denen eine Assembly ausdrücklich nicht im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20c24-108">There are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="20c24-109">Wenn Sie eine der Assemblys, aus denen eine Anwendung besteht, im globalen Assemblycache ablegen, können Sie die Anwendung anschließend weder replizieren noch installieren, indem Sie mit dem **xcopy**-Befehl das Anwendungsverzeichnis kopieren.</span><span class="sxs-lookup"><span data-stu-id="20c24-109">If you place one of the assemblies that make up an application in the global assembly cache, you can no longer replicate or install the application by using the **xcopy** command to copy the application directory.</span></span> <span data-ttu-id="20c24-110">Sie müssen die Assembly zusätzlich in den globalen Assemblycache verschieben.</span><span class="sxs-lookup"><span data-stu-id="20c24-110">You must move the assembly in the global assembly cache as well.</span></span>  
  
 <span data-ttu-id="20c24-111">Es gibt zwei Möglichkeiten für die Bereitstellung einer Assembly im globalen Assemblycache:</span><span class="sxs-lookup"><span data-stu-id="20c24-111">There are two ways to deploy an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="20c24-112">Die Verwendung eines Installationsprogramms, das für die Zusammenarbeit mit dem globalen Assemblycache entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="20c24-112">Use an installer designed to work with the global assembly cache.</span></span> <span data-ttu-id="20c24-113">Das ist die bevorzugte Option für die Installation von Assemblys im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="20c24-113">This is the preferred option for installing assemblies into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="20c24-114">Die Verwendung des Entwicklertools [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) aus [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20c24-114">Use a developer tool called the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20c24-115">Bei Bereitstellungsszenarien sollten Sie Assemblys mit Windows Installer im globalen Assemblycache installieren.</span><span class="sxs-lookup"><span data-stu-id="20c24-115">In deployment scenarios, use Windows Installer to install assemblies into the global assembly cache.</span></span> <span data-ttu-id="20c24-116">Da das Global Assembly Cache-Tool nur die Assemblyverweiszählung und andere von Windows Installer bereitgestellte Funktionen unterstützt, sollten Sie das Tool nur in Entwicklungsszenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="20c24-116">Use the Global Assembly Cache tool only in development scenarios, because it does not provide assembly reference counting and other features provided when using the Windows Installer.</span></span>  
  
 <span data-ttu-id="20c24-117">Ab .NET Framework 4 lautet die Standardposition des globalen Assemblycache **%windir%\Microsoft.NET\assembly**.</span><span class="sxs-lookup"><span data-stu-id="20c24-117">Starting with the .NET Framework 4, the default location for the global assembly cache is **%windir%\Microsoft.NET\assembly**.</span></span> <span data-ttu-id="20c24-118">In früheren Versionen von .NET Framework lautet der Standardspeicherort **%windir%\assembly**.</span><span class="sxs-lookup"><span data-stu-id="20c24-118">In earlier versions of the .NET Framework, the default location is **%windir%\assembly**.</span></span>  
  
 <span data-ttu-id="20c24-119">Administratoren verwenden zum Schutz des Verzeichnisses systemroot oftmals eine Zugriffssteuerungsliste (ACL – Access Control List), um Schreib- und Ausführungszugriffe zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="20c24-119">Administrators often protect the systemroot directory using an access control list (ACL) to control write and execute access.</span></span> <span data-ttu-id="20c24-120">Da der globale Assemblycache in einem Unterverzeichnis des Verzeichnisses systemroot installiert ist, erbt er die ACL dieses Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="20c24-120">Because the global assembly cache is installed in a subdirectory of the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="20c24-121">Aus diesem Grund empfiehlt es sich, nur Benutzern mit Administratorrechten das Löschen von Dateien aus dem globalen Assemblycache zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="20c24-121">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
 <span data-ttu-id="20c24-122">Alle Assemblys, die im globalen Assemblycache bereitgestellt werden, müssen starke Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="20c24-122">Assemblies deployed in the global assembly cache must have a strong name.</span></span> <span data-ttu-id="20c24-123">Beim Hinzufügen einer Assembly zum globalen Assemblycache werden Integritätsprüfungen für alle Dateien vorgenommen, aus denen die Assembly besteht.</span><span class="sxs-lookup"><span data-stu-id="20c24-123">When an assembly is added to the global assembly cache, integrity checks are performed on all files that make up the assembly.</span></span> <span data-ttu-id="20c24-124">Diese Integritätsprüfungen werden vom Cache durchgeführt, um sicherzustellen, dass eine Assembly nicht manipuliert wurde (z. B. wenn eine Datei geändert wurde, aber das Manifest diese Änderung nicht widerspiegelt).</span><span class="sxs-lookup"><span data-stu-id="20c24-124">The cache performs these integrity checks to ensure that an assembly has not been tampered with, for example, when a file has changed but the manifest does not reflect the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c24-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20c24-125">See Also</span></span>  
 [<span data-ttu-id="20c24-126">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="20c24-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="20c24-127">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="20c24-127">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="20c24-128">Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="20c24-128">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
