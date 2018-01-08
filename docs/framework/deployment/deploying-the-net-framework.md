---
title: Bereitstellen von .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1320c0364b1fdc3a67d2ac99d0591f37044c36a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="9e12a-102">Bereitstellen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e12a-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="9e12a-103">In diesem Abschnitt der .NET Framework-Dokumentation werden Informationen für Entwickler bereitgestellt, die .NET Framework mit ihren Anwendungen installieren, und Administratoren, die .NET Framework in einem Netzwerk bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9e12a-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="9e12a-104">Außerdem werden Probleme bei der Aktivierung und dem Neustart im Zusammenhang mit der Bereitstellung besprochen sowie erläutert, wie der Status der .NET Framework-Installation überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="9e12a-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e12a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e12a-105">In This Section</span></span>  
 [<span data-ttu-id="9e12a-106">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="9e12a-106">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 <span data-ttu-id="9e12a-107">Es wird erklärt, wie Entwickler .NET Framework auf den Computern der Benutzer mit ihren Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="9e12a-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="9e12a-108">Bereitstellungshandbuch für Administratoren</span><span class="sxs-lookup"><span data-stu-id="9e12a-108">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
 <span data-ttu-id="9e12a-109">Hierin wird erläutert, wie ein Systemadministrator mit System Center Configuration Manager (SCCM) .NET Framework und dessen Systemabhängigkeiten in einem Netzwerk bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="9e12a-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="9e12a-110">Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen</span><span class="sxs-lookup"><span data-stu-id="9e12a-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
 <span data-ttu-id="9e12a-111">Beschreibt den Neustart-Manager, der Neustarts nach Möglichkeit verhindert, und erläutert, wie Anwendungen, mit denen .NET Framework installiert wird, den Neustart-Manager nutzen können.</span><span class="sxs-lookup"><span data-stu-id="9e12a-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="9e12a-112">Gewusst wie: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9e12a-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="9e12a-113">Beschreibt, wie der .NET Framework-Setupvorgang automatisch gestartet und nachverfolgt und dabei eine eigene Ansicht des Setupstatus angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e12a-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="9e12a-114">.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="9e12a-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="9e12a-115">In diesem Artikel wird erläutert, was geschieht, wenn eine .NET Framework-Anwendung eine ungültige oder auf dem Benutzercomputer nicht installierte CLR-Version erfordert, wie diese Fehler behoben werden, und wie die Fehlermeldung, die dem Benutzer angezeigt wird, gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="9e12a-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="9e12a-116">Vorgehensweise: Debuggen von CLR-Aktivierungsproblemen</span><span class="sxs-lookup"><span data-stu-id="9e12a-116">How to: Debug CLR Activation Issues</span></span>](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="9e12a-117">Hierin wird besprochen, wie Sie CLR-Aktivierungsprotokolle anzeigen und debuggen, um Probleme zu beheben, die bei der Einrichtung Ihrer Anwendung mit der richtigen CLR-Version auftreten können.</span><span class="sxs-lookup"><span data-stu-id="9e12a-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e12a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e12a-118">See Also</span></span>  
 [<span data-ttu-id="9e12a-119">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="9e12a-119">Development Guide</span></span>](../../../docs/framework/development-guide.md)
