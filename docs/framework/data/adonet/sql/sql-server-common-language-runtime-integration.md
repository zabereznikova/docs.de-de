---
title: Common Language Runtime-Integration in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de415a6282b1d27d803d448bd3225355c08e011b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="b4081-102">Common Language Runtime-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4081-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="b4081-103">In SQL Server 2005 wurde die CLR-Komponente von .NET Framework für Microsoft Windows eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b4081-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="b4081-104">Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (STVF, Streaming Table-Valued Function) in jeder beliebigen .NET Framework-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C#, geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b4081-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="b4081-105">Der <xref:Microsoft.SqlServer.Server>-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen (APIs), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server-Umgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b4081-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="b4081-106">In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.</span><span class="sxs-lookup"><span data-stu-id="b4081-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="b4081-107">In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="b4081-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="b4081-108">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4081-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="b4081-109">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="b4081-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="b4081-110">Common Language Runtime (CLR) Integration Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="b4081-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="b4081-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b4081-111">In This Section</span></span>  
 [<span data-ttu-id="b4081-112">Einführung in die CLR-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4081-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="b4081-113">Stellt eine Einführung in die CLR-Integration in SQL Server bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="b4081-114">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b4081-115">Benutzerdefinierte CLR-Funktionen</span><span class="sxs-lookup"><span data-stu-id="b4081-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="b4081-116">Beschreibt das Implementieren und Verwenden der verschiedenen Arten von CLR-Funktionen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b4081-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="b4081-117">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="b4081-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="b4081-118">Beschreibt das Implementieren und Verwenden von benutzerdefinierten CLR-Typen.</span><span class="sxs-lookup"><span data-stu-id="b4081-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="b4081-119">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b4081-120">Gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b4081-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="b4081-121">Beschreibt das Implementieren und Verwenden von gespeicherten CLR-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="b4081-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="b4081-122">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b4081-123">CLR-Auslöser</span><span class="sxs-lookup"><span data-stu-id="b4081-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="b4081-124">Beschreibt das Implementieren und Verwenden von CLR-Triggern.</span><span class="sxs-lookup"><span data-stu-id="b4081-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="b4081-125">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b4081-126">Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="b4081-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="b4081-127">Beschreibt die Kontextverbindung.</span><span class="sxs-lookup"><span data-stu-id="b4081-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="b4081-128">Prozessinternes spezifisches Verhalten von ADO.NET in SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4081-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="b4081-129">Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext.</span><span class="sxs-lookup"><span data-stu-id="b4081-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="b4081-130">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4081-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4081-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4081-131">See Also</span></span>  
 [<span data-ttu-id="b4081-132">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b4081-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="b4081-133">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="b4081-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="b4081-134">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b4081-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
