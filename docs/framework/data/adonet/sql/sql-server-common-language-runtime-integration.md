---
title: Common Language Runtime-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 12ae15d72644e314aa694f8d169bc8f45fa284a2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452343"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="4dade-102">Common Language Runtime-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4dade-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="4dade-103">In SQL Server 2005 wurde die CLR-Komponente von .NET Framework für Microsoft Windows eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4dade-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="4dade-104">Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (STVF, Streaming Table-Valued Function) in jeder beliebigen .NET Framework-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C#, geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4dade-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="4dade-105">Der <xref:Microsoft.SqlServer.Server>-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen (APIs), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server-Umgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4dade-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="4dade-106">In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.</span><span class="sxs-lookup"><span data-stu-id="4dade-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="4dade-107">In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="4dade-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="4dade-108">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dade-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="4dade-109">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="4dade-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="4dade-110">Programmierkonzepte für die Common Language Runtime (CLR)-Integration</span><span class="sxs-lookup"><span data-stu-id="4dade-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="4dade-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4dade-111">In This Section</span></span>  
 [<span data-ttu-id="4dade-112">Einführung in die CLR-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4dade-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="4dade-113">Stellt eine Einführung in die CLR-Integration in SQL Server bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="4dade-114">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="4dade-115">CLR-benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="4dade-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="4dade-116">Beschreibt die Implementierung und Verwendung der unterschiedlichen CLR-Funktionstypen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="4dade-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="4dade-117">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="4dade-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="4dade-118">Beschreibt die Implementierung und Verwendung von CLR-benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="4dade-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="4dade-119">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="4dade-120">CLR-gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4dade-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="4dade-121">Beschreibt die Implementierung und Verwendung von CLR-gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4dade-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="4dade-122">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="4dade-123">CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="4dade-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="4dade-124">Beschreibt die Implementierung und Verwendung von CLR-Triggern.</span><span class="sxs-lookup"><span data-stu-id="4dade-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="4dade-125">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="4dade-126">Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="4dade-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="4dade-127">Beschreibt die Kontextverbindung.</span><span class="sxs-lookup"><span data-stu-id="4dade-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="4dade-128">Prozessinternes spezifisches Verhalten von ADO.NET in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4dade-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="4dade-129">Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext.</span><span class="sxs-lookup"><span data-stu-id="4dade-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="4dade-130">Stellt Links für weitere Themen bereit.</span><span class="sxs-lookup"><span data-stu-id="4dade-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dade-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dade-131">See also</span></span>

- [<span data-ttu-id="4dade-132">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4dade-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="4dade-133">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4dade-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
