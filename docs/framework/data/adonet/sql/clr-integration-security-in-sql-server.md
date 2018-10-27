---
title: CLR-Integrationssicherheit in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: dfd99155e42f426eeb01c89c433955cc2e3f0178
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454355"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="9b9b2-102">CLR-Integrationssicherheit in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b9b2-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="9b9b2-103">Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="9b9b2-104">Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="9b9b2-105">Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="9b9b2-106">In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="9b9b2-107">SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9b9b2-108">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9b9b2-108">External Resources</span></span>  
 <span data-ttu-id="9b9b2-109">Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="9b9b2-110">Ressource</span><span class="sxs-lookup"><span data-stu-id="9b9b2-110">Resource</span></span>|<span data-ttu-id="9b9b2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b9b2-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="9b9b2-112">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="9b9b2-112">Code Access Security</span></span>](../../../../../docs/framework/misc/code-access-security.md)|<span data-ttu-id="9b9b2-113">Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="9b9b2-114">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="9b9b2-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="9b9b2-115">Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b9b2-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b9b2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b9b2-116">See Also</span></span>  
 [<span data-ttu-id="9b9b2-117">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="9b9b2-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="9b9b2-118">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b9b2-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="9b9b2-119">Common Language Runtime-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b9b2-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="9b9b2-120">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9b9b2-120">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)
