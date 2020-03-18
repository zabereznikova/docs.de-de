---
title: .NET Framework-Dokumentation
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
ms.openlocfilehash: d94d97cd1b519025ff360dc903558ea3656818d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181535"
---
# <a name="net-framework-guide"></a><span data-ttu-id="01e24-102">Leitfaden für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="01e24-102">.NET Framework guide</span></span>

> [!NOTE]
> <span data-ttu-id="01e24-103">Dieser .NET Framework-Inhaltssatz enthält Informationen für die .NET Framework-Versionen 4.5 bis 4.8.</span><span class="sxs-lookup"><span data-stu-id="01e24-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="01e24-104">Weitere Informationen zum Herunterladen von .NET Framework finden Sie unter [Installieren von .NET Framework](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-104">To download .NET Framework, see [Install .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="01e24-105">Eine Liste der neuen Features und Änderungen in .NET Framework finden Sie unter [Neuerungen in .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-105">For a list of new features and changes in .NET Framework, see [What's New in .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="01e24-106">Eine Liste der unterstützten Plattformen finden Sie unter [Systemanforderungen für .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="01e24-107">Dokumentation zu früheren Versionen von .NET Framework finden Sie unter [Dokumentation zu vorherigen .NET Framework-Versionen](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="01e24-107">For documentation about older versions of .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="01e24-108">.NET Framework ist eine Entwicklungsplattform zum Erstellen von Apps für Web, Windows, Windows Server und Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="01e24-108">.NET Framework is a development platform for building apps for web, Windows, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="01e24-109">Es besteht aus der Common Language Runtime (CLR) und der .NET Framework-Klassenbibliothek, die eine breite Palette von Funktionen sowie Unterstützung für viele Branchenstandards bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="01e24-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="01e24-110">.NET Framework stellt viele Dienste bereit, einschließlich der Verwaltung des Arbeitsspeichers, Sicherheit für den Typ und Arbeitsspeicher, Sicherheit sowie Netzwerk- und Anwendungsbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="01e24-110">.NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="01e24-111">Es bietet einfach zu bedienende Datenstrukturen und APIs, die auf niedrigerer Ebene des Windows-Betriebssystems abstrahieren.</span><span class="sxs-lookup"><span data-stu-id="01e24-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="01e24-112">Sie können mit .NET Framework verschiedene Programmiersprachen verwenden, einschließlich C#, F# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="01e24-112">You can use different programming languages with .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="01e24-113">Eine allgemeine Einführung in .NET Framework für Benutzer und Entwickler erhalten Sie unter [Erste Schritte](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-113">For a general introduction to .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="01e24-114">Eine Einführung in die Architektur und die Hauptfunktionen von .NET Framework finden Sie unter [Übersicht](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-114">For an introduction to the architecture and key features of .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="01e24-115">.NET Framework kann mit Docker und mit [Windows-Containern](/virtualization/windowscontainers/about/) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01e24-115">.NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="01e24-116">Installation</span><span class="sxs-lookup"><span data-stu-id="01e24-116">Installation</span></span>

<span data-ttu-id="01e24-117">.NET Framework ist im Lieferumgang von Windows enthalten. So können Sie .NET Framework-Anwendungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="01e24-117">.NET Framework comes with Windows, which enables you to run .NET Framework applications.</span></span> <span data-ttu-id="01e24-118">Sie benötigen möglicherweise eine höhere Version von .NET Framework als die in Ihrer Windows-Version vorhandene.</span><span class="sxs-lookup"><span data-stu-id="01e24-118">You may need a later version of .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="01e24-119">Weitere Informationen finden Sie unter [Installieren von .NET Framework unter Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-119">For more information, see [Install .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="01e24-120">Lesen Sie [Reparieren von .NET Framework](./install/repair.md), um zu erfahren, wie Sie Ihre .NET Framework-Installation reparieren, wenn bei der Installation von .NET Framework Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="01e24-120">To learn how to repair your .NET Framework installation if you're experiencing errors during installation, see [Repair .NET Framework](./install/repair.md).</span></span>

<span data-ttu-id="01e24-121">Ausführlichere Informationen zum Herunterladen von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="01e24-121">For more detailed information on downloading .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="01e24-122">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="01e24-122">In this section</span></span>

* [<span data-ttu-id="01e24-123">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="01e24-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="01e24-124">Beschreibt wichtige Funktionen und Änderungen in den neuesten Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01e24-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="01e24-125">Enthält Listen von veralteten Typen und Membern sowie eine Führungslinie für das Migrieren der Anwendungen aus der früheren Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01e24-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="01e24-126">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="01e24-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="01e24-127">Stellt eine umfassende Übersicht über .NET Framework und Links zu zusätzlichen Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="01e24-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="01e24-128">Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="01e24-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="01e24-129">Enthält Ressourcen und Anleitungen zur Installation von .NET Framework und Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="01e24-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="01e24-130">Migrationshandbuch</span><span class="sxs-lookup"><span data-stu-id="01e24-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="01e24-131">Stellt Ressourcen und eine Liste der Änderungen bereit, die Sie berücksichtigen müssen, wenn Sie Ihre Anwendung zu einer neuen Version von .NET Framework migrieren.</span><span class="sxs-lookup"><span data-stu-id="01e24-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="01e24-132">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="01e24-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="01e24-133">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="01e24-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="01e24-134">Extras</span><span class="sxs-lookup"><span data-stu-id="01e24-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="01e24-135">Beschreibt die Tools, die Sie beim Entwickeln, Konfigurieren und Bereitstellen von Anwendungen mithilfe der .NET Framework-Technologien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01e24-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="01e24-136">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="01e24-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="01e24-137">Stellt Dokumentation für private .NET Framework-APIs bereit, die von Microsoft-Tools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01e24-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="01e24-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01e24-138">See also</span></span>

* [<span data-ttu-id="01e24-139">.NET Framework-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="01e24-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
