---
title: Entwickeln von Windows-Dienstanwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "43886408"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="acd90-102">Entwickeln von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="acd90-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="acd90-103">Über Microsoft Visual Studio oder das Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK können Dienste problemlos erstellt werden, indem eine Anwendung erstellt und als Dienst installiert wird.</span><span class="sxs-lookup"><span data-stu-id="acd90-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="acd90-104">Dieser Anwendungstyp wird als Windows-Dienst bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="acd90-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="acd90-105">Mit Frameworkfeatures können Sie Dienste erstellen, diese installieren, starten, beenden oder auch auf andere Weise deren Verhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="acd90-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="acd90-106">Die Windows-Dienstvorlage für C++ war in Visual Studio 2010 nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="acd90-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="acd90-107">Um einen Windows-Dienst zu erstellen, können Sie entweder einen Dienst in verwaltetem Code in Visual C# oder Visual Basic erstellen, der ggf. mit vorhandenem C++-Code zusammenarbeitet, oder Sie können über den [ATL-Projekt-Assistenten](/cpp/atl/reference/atl-project-wizard) einen Windows-Dienst in der nativen Sprache C++ erstellen.</span><span class="sxs-lookup"><span data-stu-id="acd90-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acd90-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="acd90-108">In This Section</span></span>  
 [<span data-ttu-id="acd90-109">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="acd90-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="acd90-110">Stellt eine Übersicht von Windows-Dienstanwendungen bereit, wie die Lebensdauer eines Dienst und wie Dienstanwendungen sich von anderen häufigen Projekttypen unterscheiden</span><span class="sxs-lookup"><span data-stu-id="acd90-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="acd90-111">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer</span><span class="sxs-lookup"><span data-stu-id="acd90-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="acd90-112">Stellt ein Beispiel zur Erstellung eines Diensts in Visual Basic und Visual C# bereit</span><span class="sxs-lookup"><span data-stu-id="acd90-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="acd90-113">Programmierarchitektur für Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="acd90-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="acd90-114">Erläutert die Sprachelemente, die in der Dienstprogrammierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="acd90-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="acd90-115">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="acd90-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="acd90-116">Beschreibt den Vorgang des Erstellens und Konfigurierens von Windows-Diensten über die Windows-Dienstprojektvorlage</span><span class="sxs-lookup"><span data-stu-id="acd90-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="acd90-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="acd90-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="acd90-118">Beschreibt die Hauptfeatures der <xref:System.ServiceProcess.ServiceBase>-Klasse, die zum Erstellen von Diensten verwendet wird</span><span class="sxs-lookup"><span data-stu-id="acd90-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="acd90-119">Beschreibt die Features der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceInstaller>-Klasse zum Installieren und Deinstallieren Ihrer Dienste verwendet wird</span><span class="sxs-lookup"><span data-stu-id="acd90-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="acd90-120">Beschreibt die Features der <xref:System.ServiceProcess.ServiceInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse zum Installieren und Deinstallieren Ihres Diensts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="acd90-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="acd90-121">NIB: Erstellen von Projekten aus Vorlagen</span><span class="sxs-lookup"><span data-stu-id="acd90-121">NIB Creating Projects from Templates</span></span>](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="acd90-122">Beschreibt die Projekttypen, die in diesem Kapitel verwendet werden und wie Sie aus Ihnen wählen</span><span class="sxs-lookup"><span data-stu-id="acd90-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
