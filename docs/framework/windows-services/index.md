---
title: Entwickeln von Windows-Dienstanwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 17d4c5908929f02077b1eb48932a50e83f48d076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="28f3e-102">Entwickeln von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="28f3e-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="28f3e-103">Mithilfe von Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder der Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, Sie Dienste können problemlos erstellt durch das Erstellen einer Anwendung, die als Dienst installiert ist.</span><span class="sxs-lookup"><span data-stu-id="28f3e-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="28f3e-104">Diese Art von Anwendung wird einen Windows-Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="28f3e-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="28f3e-105">Framework-Funktionen können Sie Dienste erstellen, zu installieren und starten, beenden und Steuern des Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="28f3e-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="28f3e-106">Die Windows-Dienstvorlage für C++ war nicht in Visual Studio 2010 enthalten.</span><span class="sxs-lookup"><span data-stu-id="28f3e-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="28f3e-107">Um ein Windows-Dienst zu erstellen, können Sie entweder einen Dienst erstellen, in verwaltetem Code in Visual c# oder Visual Basic, die mit vorhandenen C++-Code ggf. zusammenarbeiten kann, oder Sie können einen Windows-Dienst in systemeigenem C++ erstellen, mit der [ATL-Projekt-Assistent](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="28f3e-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28f3e-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="28f3e-108">In This Section</span></span>  
 [<span data-ttu-id="28f3e-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="28f3e-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="28f3e-110">Bietet einen Überblick über die Windows-dienstanwendungen, die Lebensdauer von einem Dienst und dienstanwendungen wie von anderen gängigen Arten des Projekts zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="28f3e-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="28f3e-111">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer</span><span class="sxs-lookup"><span data-stu-id="28f3e-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="28f3e-112">Enthält ein Beispiel zum Erstellen eines Diensts in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] und Visual c#.</span><span class="sxs-lookup"><span data-stu-id="28f3e-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="28f3e-113">Programmierarchitektur für Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="28f3e-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="28f3e-114">Erläutert die Sprachelemente in der Programmierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="28f3e-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="28f3e-115">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="28f3e-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="28f3e-116">Beschreibt den Prozess zum Erstellen und Konfigurieren von Windows-Diensten, die mit der Projektvorlage für Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="28f3e-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="28f3e-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="28f3e-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="28f3e-118">Beschreibt die wichtigsten Features von der <xref:System.ServiceProcess.ServiceBase> -Klasse, die zum Erstellen von Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="28f3e-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="28f3e-119">Beschreibt die Funktionen von der <xref:System.ServiceProcess.ServiceProcessInstaller> Klasse, die zusammen mit verwendet wird die <xref:System.ServiceProcess.ServiceInstaller> -Klasse zum Installieren und Deinstallieren von Diensten.</span><span class="sxs-lookup"><span data-stu-id="28f3e-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="28f3e-120">Beschreibt die Funktionen von der <xref:System.ServiceProcess.ServiceInstaller> Klasse, die zusammen mit verwendet wird die <xref:System.ServiceProcess.ServiceProcessInstaller> Klasse installieren und deinstallieren den Dienst.</span><span class="sxs-lookup"><span data-stu-id="28f3e-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="28f3e-121">NIB Erstellen von Projekten aus Vorlagen</span><span class="sxs-lookup"><span data-stu-id="28f3e-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="28f3e-122">Beschreibt die Typen, die in diesem Kapitel und wie Sie die Auswahl zwischen diesen verwendet.</span><span class="sxs-lookup"><span data-stu-id="28f3e-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
