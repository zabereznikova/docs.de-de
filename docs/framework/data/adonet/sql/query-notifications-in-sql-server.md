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
ms.openlocfilehash: 854407d2e6d1341d5917cc78664c1f653e55fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="e5ebd-102">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5ebd-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="e5ebd-103">Mit Abfragebenachrichtigungen, die auf der Service Broker-Infrastruktur aufsetzen, können Anwendungen benachrichtigt werden, wenn sich Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="e5ebd-104">Diese Funktion ist besonders nützlich bei Anwendungen, die Informationen aus einer Datenbank zwischenspeichern, z. B. aus einer Webanwendung, und bei Änderungen von Quelldaten benachrichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="e5ebd-105">Mithilfe von ADO.NET können Abfragebenachrichtigungen auf dreierlei Weise implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="e5ebd-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="e5ebd-106">Die konkrete Implementierung wird von der `SqlNotificationRequest`-Klasse bereitgestellt, die serverseitige Funktionen verfügbar macht und das Ausführen von Befehlen mit einer Benachrichtigungsanforderung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="e5ebd-107">Für die übergeordnete Implementierung ist die `SqlDependency`-Klasse zuständig. Diese Klasse stellt eine allgemeine Abstraktion der Benachrichtigungsfunktionalität zwischen der Quellanwendung und SQL Server bereit, die die Verwendung einer Abhängigkeit ermöglicht, um Änderungen im Server zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="e5ebd-108">In den meisten Fällen ist dies die einfachste und effektivste Art, die SQL Server-Benachrichtigungsfunktionen verwalteter Clientanwendungen mithilfe des .NET Framework-Datenanbieters für SQL Server wirkungsvoll zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="e5ebd-109">Außerdem können Webanwendungen, die mithilfe von ASP.NET 2.0 oder höher erstellt wurden, die `SqlCacheDependency`-Hilfsklassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="e5ebd-110">Abfragebenachrichtigungen werden für Anwendungen verwendet, die Anzeigen oder Zwischenspeicherungen als Antwort auf Änderungen in den zugrunde liegenden Daten aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="e5ebd-111">Microsoft SQL Server ermöglicht es .NET Framework-Anwendungen, einen Befehl an SQL Server zu senden und eine Benachrichtigung anzufordern, sobald bei der Ausführung desselben Befehls Resultsets erstellt werden, die sich von den ursprünglich abgerufenen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="e5ebd-112">Auf dem Server generierte Benachrichtigungen werden durch Warteschlangen gesendet, um später verarbeitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="e5ebd-113">Benachrichtigungen können für SELECT- und für EXECUTE-Anweisungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="e5ebd-114">Bei Verwendung einer EXECUTE-Anweisung registriert SQL Server eine Benachrichtigung für den ausgeführten Befehl und nicht für die EXECUTE-Anweisung selbst.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="e5ebd-115">Der Befehl muss den Anforderungen und Einschränkungen einer SELECT-Anweisung gerecht werden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="e5ebd-116">Wenn ein Befehl, der eine Benachrichtigung registriert, mehr als eine Anweisung enthält, erstellt das Datenbankmodul für jede Anweisung im Stapel eine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="e5ebd-117">Wenn Sie eine Anwendung entwickeln, benötigen Sie zuverlässige Sekunde Benachrichtigungen bei datenänderungen, lesen Sie die Abschnitte **Planen einer effizienten Abfragebenachrichtigungs-Strategie** und **Alternativen zur Abfrage Benachrichtigungen** in der [Planen von Benachrichtigungen](http://go.microsoft.com/fwlink/?LinkId=211984) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="e5ebd-118">Weitere Informationen zu Abfragebenachrichtigungen und SQL Server Service Broker finden Sie unter den folgenden Links zu Themen in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="e5ebd-119">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="e5ebd-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="e5ebd-120">Verwenden von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e5ebd-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="e5ebd-121">Erstellen eine Abfrage für die Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="e5ebd-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="e5ebd-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="e5ebd-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="e5ebd-123">Service Broker-Entwickler (InfoCenter)</span><span class="sxs-lookup"><span data-stu-id="e5ebd-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="e5ebd-124">Entwicklung (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="e5ebd-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="e5ebd-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e5ebd-125">In This Section</span></span>  
 [<span data-ttu-id="e5ebd-126">Aktivieren von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e5ebd-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="e5ebd-127">Erläutert die Verwendung von Abfragebenachrichtigungen und informiert über die Anforderungen, die für deren Aktivierung und Verwendung erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="e5ebd-128">"SqlDependency" in einer ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e5ebd-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="e5ebd-129">Zeigt, wie Sie Abfragebenachrichtigungen von einer ASP.NET-Anwendung aus verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="e5ebd-130">Erkennen von Änderungen mit "SqlDependency"</span><span class="sxs-lookup"><span data-stu-id="e5ebd-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="e5ebd-131">Zeigt, wie Sie erkennen können, dass sich Abfrageergebnisse von den ursprünglich empfangenen Abfrageergebnissen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="e5ebd-132">"SqlCommand"-Ausführung mit "SqlNotificationRequest"</span><span class="sxs-lookup"><span data-stu-id="e5ebd-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="e5ebd-133">Zeigt, wie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt so konfiguriert werden kann, dass es mit einer Abfragebenachrichtigung arbeitet.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e5ebd-134">Verweis</span><span class="sxs-lookup"><span data-stu-id="e5ebd-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="e5ebd-135">Beschreibt die <xref:System.Data.Sql.SqlNotificationRequest>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="e5ebd-136">Beschreibt die <xref:System.Data.SqlClient.SqlDependency>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="e5ebd-137">Beschreibt die <xref:System.Web.Caching.SqlCacheDependency>-Klasse und alle Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5ebd-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ebd-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5ebd-138">See Also</span></span>  
 [<span data-ttu-id="e5ebd-139">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5ebd-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="e5ebd-140">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e5ebd-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
