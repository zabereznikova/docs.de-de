---
title: .NET Framework 4.7, 4.6 und 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
caps.latest.revision: 75
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7f22d51a0c4fd4419fe2e499c7b0e96827696bf6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="net-framework-guide"></a><span data-ttu-id="03c1d-102">.NET Framework – Leitfaden</span><span class="sxs-lookup"><span data-stu-id="03c1d-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="03c1d-103">Dieser .NET Framework-Inhaltssatz enthält Informationen für die .NET Framework-Versionen 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2 und 4.7.</span><span class="sxs-lookup"><span data-stu-id="03c1d-103">This .NET Framework content set includes information for .NET Framework versions 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, and 4.7.</span></span> <span data-ttu-id="03c1d-104">Weitere Informationen zum Herunterladen von .NET Framework finden Sie unter [Installieren von .NET Framework](../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-104">To download the .NET Framework, see [Installing the .NET Framework](../../docs/framework/install/guide-for-developers.md).</span></span> <span data-ttu-id="03c1d-105">Eine Liste der neuen Features und Änderungen in .NET Framework 4.5, [!INCLUDE[net_v46](../../includes/net-v46-md.md)], deren Nebenversionen und .NET Framework 4.7 finden Sie unter [Neuerungen](../../docs/framework/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-105">For a list of new features and changes in the NET Framework 4.5, the [!INCLUDE[net_v46](../../includes/net-v46-md.md)], their point releases, and the .NET Framework 4.7, see [What's New in the .NET Framework](../../docs/framework/whats-new/index.md).</span></span> <span data-ttu-id="03c1d-106">Eine Liste der unterstützten Plattformen finden Sie unter [Systemanforderungen für .NET Framework](../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-106">For a list of supported platforms, see [.NET Framework System Requirements](../../docs/framework/get-started/system-requirements.md).</span></span> 

<span data-ttu-id="03c1d-107">.NET Framework ist eine Entwicklungsplattform zum Erstellen von Apps für Web, Windows, Windows Phone, Windows Server und Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="03c1d-107">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="03c1d-108">Es besteht aus der Common Language Runtime (CLR) und der .NET Framework-Klassenbibliothek, die eine breite Palette von Funktionen sowie Unterstützung für viele Branchenstandards bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="03c1d-108">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="03c1d-109">.NET Framework stellt viele Dienste bereit, einschließlich der Verwaltung des Arbeitsspeichers, Sicherheit für den Typ und Arbeitsspeicher, Sicherheit sowie Netzwerk- und Anwendungsbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03c1d-109">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="03c1d-110">Es bietet einfach zu bedienende Datenstrukturen und APIs, die auf niedrigerer Ebene des Windows-Betriebssystems abstrahieren.</span><span class="sxs-lookup"><span data-stu-id="03c1d-110">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="03c1d-111">Sie können eine Vielzahl von Programmiersprachen mit .NET Framework verwenden, einschließlich C#, F# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03c1d-111">You can use a variety of programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>  

<span data-ttu-id="03c1d-112">Eine allgemeine Einführung in .NET Framework für Benutzer und Entwickler erhalten Sie unter [Erste Schritte](../../docs/framework/get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-112">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](../../docs/framework/get-started/index.md).</span></span> <span data-ttu-id="03c1d-113">Eine Einführung in die Architektur und die Hauptfunktionen von .NET Framework finden Sie unter [Übersicht](../../docs/framework/get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-113">For an introduction to the architecture and key features of the .NET Framework, see the [overview](../../docs/framework/get-started/overview.md).</span></span>  

<span data-ttu-id="03c1d-114">.NET Framework kann mit Docker und mit [Windows-Containern](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03c1d-114">The .NET Framework can be used with Docker and with [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span> <span data-ttu-id="03c1d-115">Unter [Bereitstellen von .NET Framework-Anwendungen mit Docker](./docker/index.md) erfahren Sie, wie Sie Ihre Anwendungen mit Docker-Containern ausführen.</span><span class="sxs-lookup"><span data-stu-id="03c1d-115">See [Deploying .NET Framework applications with Docker](./docker/index.md) to learn how to run your applications in Docker containers.</span></span>

## <a name="installation"></a><span data-ttu-id="03c1d-116">Installation</span><span class="sxs-lookup"><span data-stu-id="03c1d-116">Installation</span></span>

<span data-ttu-id="03c1d-117">.NET Framework ist im Lieferumgang von Windows enthalten; so können Sie .NET Framework-Anwendungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="03c1d-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="03c1d-118">Sie benötigen möglicherweise eine höhere Version von .NET Framework als die, die mit Ihrer Windows-Version geliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="03c1d-118">You may need a later version of the .NET Framework than comes with your Windows version.</span></span> <span data-ttu-id="03c1d-119">Weitere Informationen finden Sie unter [Installieren von .NET Framework unter Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="03c1d-120">Lesen Sie [Repair the .NET Framework (Reparieren von .NET Framework)](./install/repair.md), um zu erfahren, wie Sie Ihre .NET Framework-Installation reparieren, wenn Fehler bei der Installation von .NET Framework auftreten.</span><span class="sxs-lookup"><span data-stu-id="03c1d-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you are experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="03c1d-121">Informationen zum Herunterladen von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="03c1d-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03c1d-122">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="03c1d-122">In This Section</span></span>

[<span data-ttu-id="03c1d-123">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="03c1d-123">What's New</span></span>](../../docs/framework/whats-new/index.md)  
<span data-ttu-id="03c1d-124">Beschreibt wichtige Funktionen und Änderungen in den neuesten Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03c1d-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="03c1d-125">Enthält Listen von veralteten Typen und Membern sowie eine Führungslinie für das Migrieren der Anwendungen aus der früheren Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03c1d-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="03c1d-126">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="03c1d-126">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
<span data-ttu-id="03c1d-127">Stellt eine umfassende Übersicht über .NET Framework und Links zu zusätzlichen Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="03c1d-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
<span data-ttu-id="03c1d-128">[Migrationshandbuch](../../docs/framework/migration-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="03c1d-128">[Migration Guide](../../docs/framework/migration-guide/index.md) </span></span>  
<span data-ttu-id="03c1d-129">Stellt Ressourcen und eine Liste der Änderungen bereit, die Sie berücksichtigen müssen, wenn Sie Ihre Anwendung zu einer neuen Version von .NET Framework migrieren.</span><span class="sxs-lookup"><span data-stu-id="03c1d-129">Provides resources and a list of changes you need to consider  if you're migrating your application to a new version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="03c1d-130">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="03c1d-130">Development Guide</span></span>](../../docs/framework/development-guide.md)  
<span data-ttu-id="03c1d-131">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="03c1d-131">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
[<span data-ttu-id="03c1d-132">Extras</span><span class="sxs-lookup"><span data-stu-id="03c1d-132">Tools</span></span>](../../docs/framework/tools/index.md)  
<span data-ttu-id="03c1d-133">Beschreibt die Tools, die Sie beim Entwickeln, Konfigurieren und Bereitstellen von Anwendungen mithilfe der .NET Framework-Technologien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="03c1d-133">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>  
  
<span data-ttu-id="03c1d-134">[.NET Framework-Klassenbibliothek](/dotnet/api/?view=netframework-4.7) </span><span class="sxs-lookup"><span data-stu-id="03c1d-134">[.NET Framework Class Library](/dotnet/api/?view=netframework-4.7) </span></span>  
<span data-ttu-id="03c1d-135">Stellt Syntax- und Codebeispiele sowie weitere Informationen zu jeder in den .NET Framework-Namespaces enthaltenen Klasse zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="03c1d-135">Supplies syntax, code examples, and related information for each class contained in the .NET Framework namespaces.</span></span>  
  
[<span data-ttu-id="03c1d-136">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="03c1d-136">Additional Class Libraries and APIs</span></span>](../../docs/framework/additional-apis/index.md)  
<span data-ttu-id="03c1d-137">Enthält Dokumentation für Klassen in OOB-Versionen (Out of Band) sowie für Klassen, die auf bestimmte Zielplattformen oder Implementierungen von .NET Framework ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="03c1d-137">Provides documentation for classes contained in out of band (OOB) releases, as well as for classes that target specific platforms or implementations of the .NET Framework.</span></span>

