---
title: Sicherheit in .NET
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e60f463d5a691cb84a30c169e471aa905b2db17
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728588"
---
# <a name="security-in-net"></a><span data-ttu-id="d7e92-102">Sicherheit in .NET</span><span class="sxs-lookup"><span data-stu-id="d7e92-102">Security in .NET</span></span>
<span data-ttu-id="d7e92-103">Die common Language Runtime und .NET bieten zahlreiche nützliche Klassen und Dienste, mit denen Entwickler auf einfache Weise Schreiben von sicherem Code und aktivieren zum Anpassen der Berechtigungen für Code, sodass darauf zugreifen können Systemadministratoren geschützte Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d7e92-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="d7e92-104">Darüber hinaus die Common Language Runtime und .NET nützliche Klassen und Dienste bereitgestellt, die die Verwendung von Kryptografie und rollenbasierter Sicherheit vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d7e92-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7e92-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d7e92-105">In This Section</span></span>  

 [<span data-ttu-id="d7e92-106">Schlüsselbegriffe der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7e92-106">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="d7e92-107">Übersicht über Sicherheitsfeatures der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d7e92-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="d7e92-108">Dieser Abschnitt ist für Entwickler und Systemadministratoren relevant.</span><span class="sxs-lookup"><span data-stu-id="d7e92-108">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="d7e92-109">Rollenbasierte Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7e92-109">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="d7e92-110">Beschreibt den Umgang mit rollenbasierter Sicherheit im Code.</span><span class="sxs-lookup"><span data-stu-id="d7e92-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="d7e92-111">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="d7e92-111">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d7e92-112">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="d7e92-112">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="d7e92-113">Bietet eine Übersicht über kryptografische Dienste von .NET.</span><span class="sxs-lookup"><span data-stu-id="d7e92-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="d7e92-114">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="d7e92-114">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d7e92-115">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="d7e92-115">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="d7e92-116">Beschreibt einige bewährte Methoden zum Erstellen von zuverlässigen .NET Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d7e92-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="d7e92-117">Dieser Abschnitt ist für Entwickler relevant.</span><span class="sxs-lookup"><span data-stu-id="d7e92-117">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d7e92-118">Richtlinien für das Schreiben von sicherem, nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="d7e92-118">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="d7e92-119">Beschreibt einige bewährte Methoden und Sicherheitsaspekte für das Aufrufen von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="d7e92-119">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="d7e92-120">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d7e92-120">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="d7e92-121">Beschreibt, wie Sie die anspruchsbasierte Identität in Anwendungen implementieren können.</span><span class="sxs-lookup"><span data-stu-id="d7e92-121">Describes how you can implement claims-based identity in your applications.</span></span>  

<span data-ttu-id="d7e92-122">[Änderungen der Sicherheit](../../../docs/framework/security/security-changes.md) beschreibt wichtige Änderungen am .NET Framework-Sicherheitssystem.</span><span class="sxs-lookup"><span data-stu-id="d7e92-122">[Security Changes](../../../docs/framework/security/security-changes.md) Describes important changes to the .NET Framework security system.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d7e92-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d7e92-123">Related Sections</span></span>  
 [<span data-ttu-id="d7e92-124">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d7e92-124">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="d7e92-125">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="d7e92-125">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
