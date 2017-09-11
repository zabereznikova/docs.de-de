---
title: "Sicherheit in .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .NET Framework, security
- security [.NET Framework], about security
- application development [.NET Framework], security
- security [.NET Framework]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
caps.latest.revision: 37
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b2c487c76a6a0b42370b7b70099d5baba58f42db
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---
# <a name="security-in-the-net-framework"></a><span data-ttu-id="0e52a-102">Sicherheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0e52a-102">Security in the .NET Framework</span></span>
<span data-ttu-id="0e52a-103">Die Common Language Runtime und .NET Framework stellen zahlreiche nützliche Klassen und Dienste bereit, mit denen Entwickler sicheren Code einfach schreiben und Systemadministratoren die Berechtigungen für Code anpassen können, sodass dieser auf geschützte Ressourcen zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0e52a-103">The common language runtime and the .NET Framework provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="0e52a-104">Zusätzlich werden von der Common Language Runtime und von .NET Framework Klassen und Dienste bereitgestellt, die den Einsatz kryptografischer und rollenbasierter Sicherheitsfunktionen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="0e52a-104">In addition, the runtime and the .NET Framework provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e52a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0e52a-105">In This Section</span></span>  
 [<span data-ttu-id="0e52a-106">Sicherheitsänderungen</span><span class="sxs-lookup"><span data-stu-id="0e52a-106">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)  
 <span data-ttu-id="0e52a-107">Beschreibt wichtige Änderungen am .NET Framework-Sicherheitssystem.</span><span class="sxs-lookup"><span data-stu-id="0e52a-107">Describes important changes to the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="0e52a-108">Schlüsselbegriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0e52a-108">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="0e52a-109">Übersicht über Sicherheitsfeatures der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0e52a-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="0e52a-110">Dieser Abschnitt ist für Entwickler und Systemadministratoren relevant.</span><span class="sxs-lookup"><span data-stu-id="0e52a-110">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="0e52a-111">Rollenbasierte Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0e52a-111">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="0e52a-112">Beschreibt den Umgang mit rollenbasierter Sicherheit im Code.</span><span class="sxs-lookup"><span data-stu-id="0e52a-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="0e52a-113">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="0e52a-113">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="0e52a-114">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="0e52a-114">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="0e52a-115">Übersicht über kryptografische Dienste von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e52a-115">Provides an overview of cryptographic services provided by the .NET Framework.</span></span> <span data-ttu-id="0e52a-116">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="0e52a-116">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="0e52a-117">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="0e52a-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="0e52a-118">Beschreibt einige bewährte Methoden für das Erstellen von zuverlässigen .NET Framework-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="0e52a-118">Describes some of the best practices for creating reliable .NET Framework applications.</span></span> <span data-ttu-id="0e52a-119">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="0e52a-119">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="0e52a-120">Richtlinien für das Schreiben von sicherem, nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="0e52a-120">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="0e52a-121">Beschreibt einige bewährte Methoden und Sicherheitsaspekte für das Aufrufen von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="0e52a-121">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="0e52a-122">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="0e52a-122">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="0e52a-123">Beschreibt, wie Sie die anspruchsbasierte Identität in Anwendungen implementieren können.</span><span class="sxs-lookup"><span data-stu-id="0e52a-123">Describes how you can implement claims-based identity in your applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0e52a-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0e52a-124">Related Sections</span></span>  
 [<span data-ttu-id="0e52a-125">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="0e52a-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="0e52a-126">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="0e52a-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

