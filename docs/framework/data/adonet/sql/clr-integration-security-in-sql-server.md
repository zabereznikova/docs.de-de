---
title: CLR-Integrationssicherheit in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: e5d15b4e5ac36f7ecddf45179c65a60995a1a578
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147774"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="01554-102">CLR-Integrationssicherheit in SQL Server</span><span class="sxs-lookup"><span data-stu-id="01554-102">CLR Integration Security in SQL Server</span></span>

<span data-ttu-id="01554-103">Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert.</span><span class="sxs-lookup"><span data-stu-id="01554-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="01554-104">Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.</span><span class="sxs-lookup"><span data-stu-id="01554-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="01554-105">Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="01554-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="01554-106">In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt.</span><span class="sxs-lookup"><span data-stu-id="01554-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="01554-107">SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.</span><span class="sxs-lookup"><span data-stu-id="01554-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="01554-108">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="01554-108">External Resources</span></span>  

 <span data-ttu-id="01554-109">Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="01554-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="01554-110">Resource</span><span class="sxs-lookup"><span data-stu-id="01554-110">Resource</span></span>|<span data-ttu-id="01554-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01554-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="01554-112">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="01554-112">Code Access Security</span></span>](../../../misc/code-access-security.md)|<span data-ttu-id="01554-113">Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="01554-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="01554-114">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="01554-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="01554-115">Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01554-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01554-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01554-116">See also</span></span>

- [<span data-ttu-id="01554-117">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="01554-117">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="01554-118">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="01554-118">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="01554-119">Common Language Runtime-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="01554-119">SQL Server Common Language Runtime Integration</span></span>](sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="01554-120">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01554-120">ADO.NET Overview</span></span>](../ado-net-overview.md)
