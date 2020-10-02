---
title: Entwickeln von Windows-Dienstanwendungen
description: Hier finden Sie Links zu Artikeln, in denen erläutert wird, wie Sie Windows-Dienst-Apps mit Visual Studio oder dem .NET SDK entwickeln.
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
ms.openlocfilehash: 2aea73267f05340930a9591f430de59677c1cb11
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609576"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="371b4-103">Entwickeln von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="371b4-103">Develop Windows service apps</span></span>

<span data-ttu-id="371b4-104">Über Visual Studio oder das Microsoft .NET Framework SDK können Dienste problemlos erstellt werden, indem eine Anwendung erstellt und als Dienst installiert wird.</span><span class="sxs-lookup"><span data-stu-id="371b4-104">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="371b4-105">Dieser Anwendungstyp wird als Windows-Dienst bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="371b4-105">This type of application is called a Windows service.</span></span> <span data-ttu-id="371b4-106">Mit Frameworkfeatures können Sie Dienste erstellen, diese installieren, starten, beenden oder auch auf andere Weise deren Verhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="371b4-106">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="371b4-107">In Visual Studio können Sie einen Dienst in verwaltetem Code in Visual C# oder Visual Basic erstellen, der mit vorhandenem C++-Code interagieren kann, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="371b4-107">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="371b4-108">Alternativ können Sie mithilfe des [ATL-Projekt-Assistenten](/cpp/atl/reference/atl-project-wizard) einen Windows-Dienst in nativem C++ erstellen.</span><span class="sxs-lookup"><span data-stu-id="371b4-108">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="371b4-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="371b4-109">In this section</span></span>

[<span data-ttu-id="371b4-110">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="371b4-110">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="371b4-111">Stellt eine Übersicht von Windows-Dienstanwendungen bereit, wie die Lebensdauer eines Dienst und wie Dienstanwendungen sich von anderen häufigen Projekttypen unterscheiden</span><span class="sxs-lookup"><span data-stu-id="371b4-111">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="371b4-112">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="371b4-112">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="371b4-113">Stellt ein Beispiel zur Erstellung eines Diensts in Visual Basic und Visual C# bereit</span><span class="sxs-lookup"><span data-stu-id="371b4-113">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="371b4-114">Programmierarchitektur für Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="371b4-114">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="371b4-115">Erläutert die Sprachelemente, die in der Dienstprogrammierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="371b4-115">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="371b4-116">How to: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="371b4-116">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="371b4-117">Beschreibt den Vorgang des Erstellens und Konfigurierens von Windows-Diensten über die Windows-Dienstprojektvorlage</span><span class="sxs-lookup"><span data-stu-id="371b4-117">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="371b4-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="371b4-118">Related sections</span></span>

<span data-ttu-id="371b4-119"><xref:System.ServiceProcess.ServiceBase>: Beschreibt die Hauptfeatures der <xref:System.ServiceProcess.ServiceBase>-Klasse, die zum Erstellen von Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="371b4-119"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="371b4-120"><xref:System.ServiceProcess.ServiceProcessInstaller>: Beschreibt die Features der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceInstaller>-Klasse zum Installieren und Deinstallieren Ihres Diensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="371b4-120"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="371b4-121"><xref:System.ServiceProcess.ServiceInstaller>: Beschreibt die Features der <xref:System.ServiceProcess.ServiceInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse zum Installieren und Deinstallieren Ihres Diensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="371b4-121"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="371b4-122">[Erstellen von Projekten aus Vorlagen](/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)): Beschreibt die Projekttypen, die in diesem Kapitel verwendet werden und wie Sie Ihre Wahl unter ihnen treffen.</span><span class="sxs-lookup"><span data-stu-id="371b4-122">[Create Projects from Templates](/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
