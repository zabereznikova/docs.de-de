---
title: "Übersicht über die SQL Server-Sicherheit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a8f44b69f177584bb3680f68c50ff054c6b805ed
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="overview-of-sql-server-security"></a><span data-ttu-id="adf1b-102">Übersicht über die SQL Server-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="adf1b-102">Overview of SQL Server Security</span></span>
<span data-ttu-id="adf1b-103">Sicherheitsbedrohungen können Sie am besten mit einer tiefgestaffelten Verteidigungsstrategie mit sich überschneidenden Sicherheitsebenen begegnen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-103">A defense-in-depth strategy, with overlapping layers of security, is the best way to counter security threats.</span></span> <span data-ttu-id="adf1b-104">SQL Server bietet eine Sicherheitsarchitektur, die es Datenbankadministratoren und Entwicklern erlaubt, sichere Datenbankanwendungen zu erstellen und ihre Anwendungen vor Sicherheitsrisiken zu schützen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-104">SQL Server provides a security architecture that is designed to allow database administrators and developers to create secure database applications and counter threats.</span></span> <span data-ttu-id="adf1b-105">Jede neue SQL Server-Version ist durch die Einführung neuer Funktionen und Funktionalität besser als die vorherige Version.</span><span class="sxs-lookup"><span data-stu-id="adf1b-105">Each version of SQL Server has improved on previous versions of SQL Server with the introduction of new features and functionality.</span></span> <span data-ttu-id="adf1b-106">Aber Sicherheit gibt es nicht einfach ab Fabrik.</span><span class="sxs-lookup"><span data-stu-id="adf1b-106">However, security does not ship in the box.</span></span> <span data-ttu-id="adf1b-107">Jede Anwendung hat ihre eigenen Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-107">Each application is unique in its security requirements.</span></span> <span data-ttu-id="adf1b-108">Entwickler müssen ein klares Bild davon haben, welche Kombination aus Funktionen und Funktionalität sich zur Abwehr der bekannten Risiken am besten eignet, und sie müssen zukünftig auftretende Risiken vorhersehen können.</span><span class="sxs-lookup"><span data-stu-id="adf1b-108">Developers need to understand which combination of features and functionality are most appropriate to counter known threats, and to anticipate threats that may arise in the future.</span></span>  
  
 <span data-ttu-id="adf1b-109">Eine SQL Server-Instanz enthält, angefangen mit dem Server, eine hierarchisch strukturierte Sammlung von Entitäten.</span><span class="sxs-lookup"><span data-stu-id="adf1b-109">A SQL Server instance contains a hierarchical collection of entities, starting with the server.</span></span> <span data-ttu-id="adf1b-110">Auf jedem Server befinden sich mehrere Datenbanken, und jede Datenbank enthält eine Sammlung sicherungsfähiger Objekte.</span><span class="sxs-lookup"><span data-stu-id="adf1b-110">Each server contains multiple databases, and each database contains a collection of securable objects.</span></span> <span data-ttu-id="adf1b-111">Jedem sicherungsfähigen SQL Server verfügt über zugeordnete *Berechtigungen* zu gewährt werden können eine *principal*, dies ist eine einzelne, Gruppe oder Prozess gewährt Zugriff auf SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adf1b-111">Every SQL Server securable has associated *permissions* that can be granted to a *principal*, which is an individual, group or process granted access to SQL Server.</span></span> <span data-ttu-id="adf1b-112">Die SQL Server-Sicherheitsframework verwaltet den Zugriff auf die sicherungsfähigen Entitäten *Authentifizierung* und *Autorisierung*.</span><span class="sxs-lookup"><span data-stu-id="adf1b-112">The SQL Server security framework manages access to securable entities through *authentication* and *authorization*.</span></span>  
  
-   <span data-ttu-id="adf1b-113">Die Authentifizierung ist der Prozess der Anmeldung bei SQL Server. Ein Prinzipal fordert dabei unter Angabe seiner Anmeldeinformationen, die vom Server ausgewertet werden, den Zugriff an.</span><span class="sxs-lookup"><span data-stu-id="adf1b-113">Authentication is the process of logging on to SQL Server by which a principal requests access by submitting credentials that the server evaluates.</span></span> <span data-ttu-id="adf1b-114">Die Authentifizierung stellt die Identität des Benutzers oder Prozesses her, der authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="adf1b-114">Authentication establishes the identity of the user or process being authenticated.</span></span>  
  
-   <span data-ttu-id="adf1b-115">Bei der Autorisierung wird ermittelt, auf welche sicherungsfähigen Ressourcen ein Prinzipal zugreifen kann und welche Vorgänge für diese Ressourcen erlaubt sind.</span><span class="sxs-lookup"><span data-stu-id="adf1b-115">Authorization is the process of determining which securable resources a principal can access, and which operations are allowed for those resources.</span></span>  
  
 <span data-ttu-id="adf1b-116">Die Themen in diesem Abschnitt enthalten grundlegende Informationen zur SQL Server-Sicherheit sowie Links zur jeweiligen vollständigen SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="adf1b-116">The topics in this section cover SQL Server security fundamentals, providing links to the complete documentation in the relevant version of SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="adf1b-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="adf1b-117">In This Section</span></span>  
 [<span data-ttu-id="adf1b-118">Authentifizierung in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-118">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 <span data-ttu-id="adf1b-119">Beschreibt die Anmeldungen und die Authentifizierung in SQL Server und enthält Links zu weiteren Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-119">Describes logins and authentication in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="adf1b-120">Server- und Datenbankrollen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-120">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 <span data-ttu-id="adf1b-121">Beschreibt feste Serverrollen und Datenbankrollen, benutzerdefinierte Datenbankrollen sowie integrierte Konten und enthält Links zu weiteren Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-121">Describes fixed server and database roles, custom database roles, and built-in accounts and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="adf1b-122">Objektbesitz und Trennung von Benutzer und Schema in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-122">Ownership and User-Schema Separation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 <span data-ttu-id="adf1b-123">Beschreibt die Trennung von Objektbesitz und Benutzerschema und enthält Links zu weiteren Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-123">Describes object ownership and  user-schema separation and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="adf1b-124">Autorisierung und Berechtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-124">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 <span data-ttu-id="adf1b-125">Beschreibt, wie Berechtigungen nach dem Prinzip der minimalen Rechtegewährung gewährt werden können, und enthält Links zu weiteren Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-125">Describes granting permissions using the principle of least privilege and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="adf1b-126">Datenverschlüsselung in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-126">Data Encryption in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 <span data-ttu-id="adf1b-127">Beschreibt die Datenverschlüsselungsoptionen in SQL Server und enthält Links zu weiteren Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="adf1b-127">Describes data encryption options in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="adf1b-128">CLR-Integrationssicherheit in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-128">CLR Integration Security in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 <span data-ttu-id="adf1b-129">Enthält Links zu Ressourcen zum Thema CLR-Integrationssicherheit.</span><span class="sxs-lookup"><span data-stu-id="adf1b-129">Provides links to CLR integration security resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf1b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adf1b-130">See Also</span></span>  
 [<span data-ttu-id="adf1b-131">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="adf1b-131">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="adf1b-132">SQL Server Security (SQL Server-Sicherheit)</span><span class="sxs-lookup"><span data-stu-id="adf1b-132">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [<span data-ttu-id="adf1b-133">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf1b-133">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="adf1b-134">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="adf1b-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
