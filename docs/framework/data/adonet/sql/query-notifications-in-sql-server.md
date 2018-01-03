---
title: Abfragebenachrichtigungen in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d922598cb31e60b1c1648884555695c1ba089726
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="96434-102">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="96434-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="96434-103">Mit Abfragebenachrichtigungen, die auf der Service Broker-Infrastruktur aufsetzen, können Anwendungen benachrichtigt werden, wenn sich Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="96434-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="96434-104">Diese Funktion ist besonders nützlich bei Anwendungen, die Informationen aus einer Datenbank zwischenspeichern, z. B. aus einer Webanwendung, und bei Änderungen von Quelldaten benachrichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="96434-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="96434-105">Mithilfe von ADO.NET können Abfragebenachrichtigungen auf dreierlei Weise implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="96434-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="96434-106">Die konkrete Implementierung wird von der `SqlNotificationRequest`-Klasse bereitgestellt, die serverseitige Funktionen verfügbar macht und das Ausführen von Befehlen mit einer Benachrichtigungsanforderung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="96434-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="96434-107">Für die übergeordnete Implementierung ist die `SqlDependency`-Klasse zuständig. Diese Klasse stellt eine allgemeine Abstraktion der Benachrichtigungsfunktionalität zwischen der Quellanwendung und SQL Server bereit, die die Verwendung einer Abhängigkeit ermöglicht, um Änderungen im Server zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="96434-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="96434-108">In den meisten Fällen ist dies die einfachste und effektivste Art, die SQL Server-Benachrichtigungsfunktionen verwalteter Clientanwendungen mithilfe des .NET Framework-Datenanbieters für SQL Server wirkungsvoll zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="96434-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="96434-109">Außerdem können Webanwendungen, die mithilfe von ASP.NET 2.0 oder höher erstellt wurden, die `SqlCacheDependency`-Hilfsklassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="96434-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="96434-110">Abfragebenachrichtigungen werden für Anwendungen verwendet, die Anzeigen oder Zwischenspeicherungen als Antwort auf Änderungen in den zugrunde liegenden Daten aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="96434-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="96434-111">Microsoft SQL Server ermöglicht es .NET Framework-Anwendungen, einen Befehl an SQL Server zu senden und eine Benachrichtigung anzufordern, sobald bei der Ausführung desselben Befehls Resultsets erstellt werden, die sich von den ursprünglich abgerufenen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="96434-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="96434-112">Auf dem Server generierte Benachrichtigungen werden durch Warteschlangen gesendet, um später verarbeitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="96434-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="96434-113">Benachrichtigungen können für SELECT- und für EXECUTE-Anweisungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="96434-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="96434-114">Bei Verwendung einer EXECUTE-Anweisung registriert SQL Server eine Benachrichtigung für den ausgeführten Befehl und nicht für die EXECUTE-Anweisung selbst.</span><span class="sxs-lookup"><span data-stu-id="96434-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="96434-115">Der Befehl muss den Anforderungen und Einschränkungen einer SELECT-Anweisung gerecht werden.</span><span class="sxs-lookup"><span data-stu-id="96434-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="96434-116">Wenn ein Befehl, der eine Benachrichtigung registriert, mehr als eine Anweisung enthält, erstellt das Datenbankmodul für jede Anweisung im Stapel eine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="96434-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="96434-117">Wenn Sie eine Anwendung entwickeln, benötigen Sie zuverlässige Sekunde Benachrichtigungen bei datenänderungen, lesen Sie die Abschnitte **Planen einer effizienten Abfragebenachrichtigungs-Strategie** und **Alternativen zur Abfrage Benachrichtigungen** in der [Planen von Benachrichtigungen](http://go.microsoft.com/fwlink/?LinkId=211984) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="96434-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="96434-118">Weitere Informationen zu Abfragebenachrichtigungen und SQL Server Service Broker finden Sie unter den folgenden Links zu Themen in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="96434-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="96434-119">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="96434-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="96434-120">Verwenden von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="96434-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="96434-121">Erstellen eine Abfrage für die Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="96434-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="96434-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="96434-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="96434-123">Service Broker-Entwickler (InfoCenter)</span><span class="sxs-lookup"><span data-stu-id="96434-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="96434-124">Entwicklung (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="96434-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="96434-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="96434-125">In This Section</span></span>  
 [<span data-ttu-id="96434-126">Aktivieren von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="96434-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="96434-127">Erläutert die Verwendung von Abfragebenachrichtigungen und informiert über die Anforderungen, die für deren Aktivierung und Verwendung erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="96434-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="96434-128">SqlDependency in einer ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="96434-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="96434-129">Zeigt, wie Sie Abfragebenachrichtigungen von einer ASP.NET-Anwendung aus verwenden können.</span><span class="sxs-lookup"><span data-stu-id="96434-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="96434-130">Ermitteln von Änderungen mit SqlDependency</span><span class="sxs-lookup"><span data-stu-id="96434-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="96434-131">Zeigt, wie Sie erkennen können, dass sich Abfrageergebnisse von den ursprünglich empfangenen Abfrageergebnissen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="96434-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="96434-132">SqlCommand-Ausführung mit SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="96434-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="96434-133">Zeigt, wie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt so konfiguriert werden kann, dass es mit einer Abfragebenachrichtigung arbeitet.</span><span class="sxs-lookup"><span data-stu-id="96434-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96434-134">Verweis</span><span class="sxs-lookup"><span data-stu-id="96434-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="96434-135">Beschreibt die <xref:System.Data.Sql.SqlNotificationRequest>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="96434-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="96434-136">Beschreibt die <xref:System.Data.SqlClient.SqlDependency>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="96434-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="96434-137">Beschreibt die <xref:System.Web.Caching.SqlCacheDependency>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="96434-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96434-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96434-138">See Also</span></span>  
 [<span data-ttu-id="96434-139">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="96434-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="96434-140">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="96434-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
