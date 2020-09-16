---
title: Sichern von Anwendungen
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: af184f64b43c2d3dc39f8c0add08940d3b002c24
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550754"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="e86d9-102">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e86d9-102">Securing ADO.NET applications</span></span>

<span data-ttu-id="e86d9-103">Beim Schreiben von sicheren ADO.NET-Anwendungen gilt es nicht nur, häufige Fallstricke bei der Codierung zu umgehen, wie die Nichtvalidierung von Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="e86d9-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="e86d9-104">Eine Anwendung, die auf Daten zugreift, weist eine Vielzahl von möglichen Fehlern auf, die Angreifer ausnutzen können, um vertrauliche Daten abzurufen, zu ändern oder zu beschädigen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="e86d9-105">Es ist daher unerlässlich, alle Sicherheitsaspekte zu verstehen, und zwar beginnend bei der Erstellung von Gefahrenmodellen während des Anwendungsentwurfs bis hin zur eigentlichen Bereitstellung der Anwendung und ihrem laufenden Betrieb.</span><span class="sxs-lookup"><span data-stu-id="e86d9-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
<span data-ttu-id="e86d9-106">.NET Framework bietet eine Reihe nützlicher Klassen, Dienste und Tools zum Sichern und Verwalten von Datenbankanwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="e86d9-107">Die Common Language Runtime (CLR) bietet eine typsichere Umgebung für die Ausführung von Code mit Codezugriffssicherheit (Code Access Security, CAS), um die Berechtigungen für verwalteten Code weiter einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="e86d9-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="e86d9-108">Die Beachtung von Codierungspraktiken für einen sicheren Datenzugriff hilft, den Schaden zu begrenzen, den ein potenzieller Angreifer verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="e86d9-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
<span data-ttu-id="e86d9-109">Das Schreiben von sicherem Code schützt jedoch nicht vor selbst zu verantwortenden Sicherheitslücken beim Arbeiten mit nicht verwalteten Ressourcen, wie Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="e86d9-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="e86d9-110">Die meisten Serverdatenbanken, wie SQL Server, verfügen über eigene Sicherheitssysteme, die bei korrekter Implementierung für mehr Sicherheit sorgen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="e86d9-111">Aber auch Datenquellen mit einem robusten Sicherheitssystem können zum Angriffsopfer werden, wenn sie nicht ordnungsgemäß konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e86d9-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e86d9-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e86d9-112">In this section</span></span>

 [<span data-ttu-id="e86d9-113">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="e86d9-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="e86d9-114">Enthält Empfehlungen für das Entwerfen sicherer ADO.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="e86d9-115">Sicherer Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="e86d9-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="e86d9-116">Beschreibt das Arbeiten mit Daten aus einer gesicherten Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="e86d9-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="e86d9-117">Sichere Clientanwendungen</span><span class="sxs-lookup"><span data-stu-id="e86d9-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="e86d9-118">Enthält Überlegungen zum Thema Sicherheit für Clientanwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="e86d9-119">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e86d9-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="e86d9-120">Beschreibt, wie CAS zum Schutz von ADO.NET-Code beitragen kann.</span><span class="sxs-lookup"><span data-stu-id="e86d9-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="e86d9-121">Erläutert außerdem das Arbeiten mit teilweiser Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="e86d9-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="e86d9-122">Datenschutz und -sicherheit</span><span class="sxs-lookup"><span data-stu-id="e86d9-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="e86d9-123">Beschreibt Verschlüsselungsmöglichkeiten für ADO.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e86d9-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e86d9-124">Related sections</span></span>

 [<span data-ttu-id="e86d9-125">Leitfaden für DataSet und Datentabelle</span><span class="sxs-lookup"><span data-stu-id="e86d9-125">DataSet and DataTable security guidance</span></span>](dataset-datatable-dataview/security-guidance.md)  
 <span data-ttu-id="e86d9-126">Bietet Sicherheits Anleitungen für <xref:System.Data.DataSet> und <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="e86d9-126">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="e86d9-127">SQL Server Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e86d9-127">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="e86d9-128">Beschreibt SQL Server-Sicherheitsfunktionen aus Entwicklersicht.</span><span class="sxs-lookup"><span data-stu-id="e86d9-128">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="e86d9-129">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="e86d9-129">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="e86d9-130">Beschreibt Sicherheitsfunktionen für Entity Framework-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-130">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="e86d9-131">Security</span><span class="sxs-lookup"><span data-stu-id="e86d9-131">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="e86d9-132">Enthält Links zu Artikeln, in denen alle Aspekte der Sicherheit in .net beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e86d9-132">Contains links to articles describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="e86d9-133">[Sicherheitstools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e86d9-133">[Security Tools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="e86d9-134">.NET Framework-Tools zum Sichern und Verwalten von Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="e86d9-134">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="e86d9-135">[Ressourcen für das Erstellen sicherer Anwendungen](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e86d9-135">[Resources for Creating Secure Applications](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="e86d9-136">Enthält Links zu Artikeln zum Erstellen sicherer Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e86d9-136">Provides links to articles for creating secure applications.</span></span>  
  
 [<span data-ttu-id="e86d9-137">Sicherheitsbibliographie</span><span class="sxs-lookup"><span data-stu-id="e86d9-137">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="e86d9-138">Enthält Links zu externen Ressourcen, die online und in Druckversion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e86d9-138">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e86d9-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e86d9-139">See also</span></span>

- [<span data-ttu-id="e86d9-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e86d9-140">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="e86d9-141">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e86d9-141">ADO.NET Overview</span></span>](ado-net-overview.md)
