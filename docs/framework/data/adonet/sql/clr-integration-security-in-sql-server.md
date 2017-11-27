---
title: CLR-Integrationssicherheit in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4f4b1ae5ba252778d9463cba43a9ccb419600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="dade0-102">CLR-Integrationssicherheit in SQL Server</span><span class="sxs-lookup"><span data-stu-id="dade0-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="dade0-103">Die CLR (Common Language Runtime)-Komponente von .NET Framework ist in Microsoft SQL Server integriert.</span><span class="sxs-lookup"><span data-stu-id="dade0-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="dade0-104">Dank CLR-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (Streaming Table-Valued Function, STVF) in jeder beliebigen .NET Framework-Sprache (wie Microsoft Visual Basic .NET oder Microsoft Visual C#) schreiben.</span><span class="sxs-lookup"><span data-stu-id="dade0-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="dade0-105">Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit (Code Access Security, CAS) für verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="dade0-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="dade0-106">In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt.</span><span class="sxs-lookup"><span data-stu-id="dade0-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="dade0-107">SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server-Modell der benutzerbasierten Sicherheit und dem CLR-Modell der Codezugriffssicherheit.</span><span class="sxs-lookup"><span data-stu-id="dade0-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="dade0-108">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="dade0-108">External Resources</span></span>  
 <span data-ttu-id="dade0-109">Weitere Informationen zur CLR-Integration mit SQL Server finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="dade0-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="dade0-110">Ressource</span><span class="sxs-lookup"><span data-stu-id="dade0-110">Resource</span></span>|<span data-ttu-id="dade0-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dade0-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="dade0-112">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="dade0-112">Code Access Security</span></span>](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="dade0-113">Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="dade0-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="dade0-114">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="dade0-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="dade0-115">Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dade0-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dade0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dade0-116">See Also</span></span>  
 [<span data-ttu-id="dade0-117">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="dade0-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="dade0-118">Anwendungssicherheitsszenarios in SQLServer</span><span class="sxs-lookup"><span data-stu-id="dade0-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="dade0-119">SQL Server Common Language Runtime-Integration</span><span class="sxs-lookup"><span data-stu-id="dade0-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="dade0-120">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="dade0-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
