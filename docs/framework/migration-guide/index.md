---
title: 'Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5 '
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 820d1966172a93c06c6451c51bc7f360496f46b8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a><span data-ttu-id="39724-102">Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5</span><span class="sxs-lookup"><span data-stu-id="39724-102">Migration Guide to the .NET Framework 4.7, 4.6, and 4.5</span></span> 
<span data-ttu-id="39724-103">Wenn Sie Ihre Anwendung mit einer früheren Version von .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und dessen Nebenversionen (4.5.1 und 4.5.2), .NET Framework 4.6 und dessen Nebenversionen (4.6.1 und 4.6.2) oder .NET Framework 4.7 durchführen.</span><span class="sxs-lookup"><span data-stu-id="39724-103">If you created your app using an earlier version of the .NET Framework, you can generally upgrade it to the .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), the .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), or the .NET Framework 4.7 easily.</span></span> <span data-ttu-id="39724-104">Öffnen Sie Ihr Projekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="39724-104">Open your project in Visual Studio.</span></span> <span data-ttu-id="39724-105">Wenn das Projekt in einer früheren Version erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="39724-105">If your project was created in an earlier version, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="39724-106">Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2017 – Zielplattformen und Kompatibilität](https://www.visualstudio.com/en-us/productinfo/vs2017-compatibility-vs).</span><span class="sxs-lookup"><span data-stu-id="39724-106">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2017 Platform Targeting and Compatibility](https://www.visualstudio.com/en-us/productinfo/vs2017-compatibility-vs).</span></span>  
  
 <span data-ttu-id="39724-107">Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code.</span><span class="sxs-lookup"><span data-stu-id="39724-107">However, some changes in the .NET Framework require changes to your code.</span></span> <span data-ttu-id="39724-108">So möchten Sie möglicherweise die neuen Funktionen von .NET Framework 4.5 und dessen Punktreleases, von .NET Framework 4.6 und dessen Punktreleases sowie von .NET Framework 4.7 nutzen.</span><span class="sxs-lookup"><span data-stu-id="39724-108">You may also want to take advantage of functionality that is new in the .NET Framework 4.5 and its point releases, in the .NET Framework 4.6 and its point releases, or in the .NET Framework 4.7.</span></span> <span data-ttu-id="39724-109">Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="39724-109">Making these types of changes to your app for a new version of the .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="39724-110">Wenn Ihre App nicht migriert werden muss, können Sie diese in .NET Framework 4.5 oder neueren Versionen ohne Neukompilieren ausführen.</span><span class="sxs-lookup"><span data-stu-id="39724-110">If your app doesn't have to be migrated, you can run it in the .NET Framework 4.5 or later versions without recompiling it.</span></span>  
  
## <a name="migration-resources"></a><span data-ttu-id="39724-111">Migrationsressourcen</span><span class="sxs-lookup"><span data-stu-id="39724-111">Migration resources</span></span>  
 <span data-ttu-id="39724-112">Überprüfen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2 oder 4.7 migrieren:</span><span class="sxs-lookup"><span data-stu-id="39724-112">Review the following documents before you migrate your app from earlier versions of the .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, or 4.7:</span></span>  
  
-   <span data-ttu-id="39724-113">Lesen Sie [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md), damit Sie die CLR-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="39724-113">See [Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>  
  
-   <span data-ttu-id="39724-114">Lesen Sie [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md), um Informationen zu Laufzeit- und Neuausrichtungsänderungen zu erhalten, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="39724-114">Review [Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>  
  
-   <span data-ttu-id="39724-115">Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="39724-115">Review [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>  
  
-   <span data-ttu-id="39724-116">Unter [Neuigkeiten](../../../docs/framework/whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="39724-116">See [What's New](../../../docs/framework/whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39724-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39724-117">See Also</span></span>  
 <span data-ttu-id="39724-118">[Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="39724-118">[Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md) </span></span>  
 <span data-ttu-id="39724-119">[Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md) </span><span class="sxs-lookup"><span data-stu-id="39724-119">[Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md) </span></span>  
 <span data-ttu-id="39724-120">[Versionskompatibilität](../../../docs/framework/migration-guide/version-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="39724-120">[Version Compatibility](../../../docs/framework/migration-guide/version-compatibility.md) </span></span>  
 <span data-ttu-id="39724-121">[Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span><span class="sxs-lookup"><span data-stu-id="39724-121">[Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span></span>  
 <span data-ttu-id="39724-122">[Gewusst wie: Konfigurieren einer App für die Unterstützung von .NET Framework 4 oder 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md) </span><span class="sxs-lookup"><span data-stu-id="39724-122">[How to: Configure an App to Support .NET Framework 4 or 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md) </span></span>  
 <span data-ttu-id="39724-123">[Neuigkeiten](../../../docs/framework/whats-new/index.md) </span><span class="sxs-lookup"><span data-stu-id="39724-123">[What's New](../../../docs/framework/whats-new/index.md) </span></span>  
 <span data-ttu-id="39724-124">[Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md) </span><span class="sxs-lookup"><span data-stu-id="39724-124">[What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) </span></span>  
 <span data-ttu-id="39724-125">[Versions- und Assemblyinformationen zu .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701) </span><span class="sxs-lookup"><span data-stu-id="39724-125">[.NET Framework Version and Assembly Information](http://go.microsoft.com/fwlink/?LinkId=201701) </span></span>  
 <span data-ttu-id="39724-126">[Microsoft .NET Framework Support Lifecycle-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=196607) [Migrationsprobleme in .NET Framework 4](net-framework-4-migration-issues.md)</span><span class="sxs-lookup"><span data-stu-id="39724-126">[Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET Framework 4 migration issues](net-framework-4-migration-issues.md)</span></span>

