---
title: Aktivieren von Abfragebenachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: c164490464d839dacefaf570c8956bf15caeb7de
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480541"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="e2f08-102">Aktivieren von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e2f08-102">Enabling Query Notifications</span></span>
<span data-ttu-id="e2f08-103">Anwendungen, die Abfragebenachrichtigungen verwenden, haben einige Anforderungen gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="e2f08-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="e2f08-104">Ihre Datenquelle muss richtig konfiguriert sein, um SQL-Abfragebenachrichtigungen zu unterstützen, und die Benutzer müssen über die richtigen client- und serverseitigen Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="e2f08-105">Zum Verwenden von Abfragebenachrichtigungen muss Folgendes erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="e2f08-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="e2f08-106">Aktivieren von Abfragebenachrichtigungen für Ihre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e2f08-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="e2f08-107">Sicherstellen, dass die zum Verbinden mit der Datenbank verwendete Benutzer-ID über die erforderlichen Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e2f08-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="e2f08-108">Verwenden eines <xref:System.Data.SqlClient.SqlCommand>-Objekts zum Ausführen einer gültigen SELECT-Anweisung mit einem zugehörigen Benachrichtigungsobjekt, entweder <xref:System.Data.SqlClient.SqlDependency> oder <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="e2f08-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="e2f08-109">Bereitstellen von Code, um die Benachrichtigung zu verarbeiten, falls sich die überwachten Daten ändern.</span><span class="sxs-lookup"><span data-stu-id="e2f08-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="e2f08-110">Anforderungen für Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e2f08-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="e2f08-111">Abfragebenachrichtigungen werden nur für SELECT-Anweisungen unterstützt, die bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="e2f08-112">Die folgende Tabelle enthält Links zur SQL Server-Onlinedokumentation zu Service Broker und Abfragebenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="e2f08-113">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="e2f08-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="e2f08-114">Erstellen eine Abfrage für die Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="e2f08-114">Creating a Query for Notification</span></span>](https://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="e2f08-115">Überlegungen zur Sicherheit für Service Broker</span><span class="sxs-lookup"><span data-stu-id="e2f08-115">Security Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="e2f08-116">Sicherheit und Schutz (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="e2f08-116">Security and Protection (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="e2f08-117">Sicherheitsaspekte für Notification Services</span><span class="sxs-lookup"><span data-stu-id="e2f08-117">Security Considerations for Notifications Services</span></span>](https://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="e2f08-118">Berechtigungen für Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e2f08-118">Query Notification Permissions</span></span>](https://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="e2f08-119">Internationale Gesichtspunkte bei Service Broker</span><span class="sxs-lookup"><span data-stu-id="e2f08-119">International Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="e2f08-120">Überlegungen zu Lösungsentwürfen (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="e2f08-120">Solution Design Considerations (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="e2f08-121">Service Broker-Entwickler (InfoCenter)</span><span class="sxs-lookup"><span data-stu-id="e2f08-121">Service Broker Developer InfoCenter</span></span>](https://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="e2f08-122">Entwicklerhandbuch (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="e2f08-122">Developer's Guide (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="e2f08-123">Aktivieren von Abfragebenachrichtigungen für das Ausführen von Beispielcode</span><span class="sxs-lookup"><span data-stu-id="e2f08-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="e2f08-124">Zum Aktivieren von Service Broker für die **AdventureWorks** -Datenbank mithilfe des SQL Server Management Studio, führen Sie die folgende Transact-SQL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="e2f08-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="e2f08-125">Damit die Abfragebenachrichtigungsbeispiele ordnungsgemäß ausgeführt werden, müssen auf dem Datenbankserver die folgenden Transact-SQL-Anweisungen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e2f08-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="e2f08-126">Berechtigungen für Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e2f08-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="e2f08-127">Benutzer, die Befehle ausführen, mit denen Benachrichtigung angefordert werden, müssen über eine SUBSCRIBE QUERY NOTIFICATIONS-Datenbankberechtigung auf dem Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="e2f08-128">Clientseitiger Code, der in einem teilweise vertrauenswürdigen Kontext ausgeführt wird, erfordert die <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="e2f08-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="e2f08-129">Im folgenden Code wird ein <xref:System.Data.SqlClient.SqlClientPermission>-Objekt erstellt, das den <xref:System.Security.Permissions.PermissionState> auf <xref:System.Security.Permissions.PermissionState.Unrestricted> setzt.</span><span class="sxs-lookup"><span data-stu-id="e2f08-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="e2f08-130">Die <xref:System.Security.CodeAccessPermission.Demand%2A> erzwingt zur Laufzeit eine <xref:System.Security.SecurityException>, wenn nicht allen Aufrufern, die sich in der Aufrufliste darüber befinden, die Berechtigung gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2f08-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="e2f08-131">Auswählen eines Benachrichtigungsobjekts</span><span class="sxs-lookup"><span data-stu-id="e2f08-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="e2f08-132">Die Abfragebenachrichtigungs-API stellt zwei Objekte zum Verarbeiten von Benachrichtigungen zur Verfügung: <xref:System.Data.SqlClient.SqlDependency> und <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="e2f08-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="e2f08-133">Im Allgemeinen sollten die meisten Nicht-ASP.NET-Anwendungen das <xref:System.Data.SqlClient.SqlDependency>-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2f08-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="e2f08-134">ASP.NET-Anwendungen sollten die übergeordnete <xref:System.Web.Caching.SqlCacheDependency> verwenden, die die <xref:System.Data.SqlClient.SqlDependency> umschließt und einen Rahmen für die Verwaltung der Benachrichtigungs- und Zwischenspeicherobjekte bietet.</span><span class="sxs-lookup"><span data-stu-id="e2f08-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="e2f08-135">Verwenden von "SqlDependency"</span><span class="sxs-lookup"><span data-stu-id="e2f08-135">Using SqlDependency</span></span>  
 <span data-ttu-id="e2f08-136">Zum Verwenden des <xref:System.Data.SqlClient.SqlDependency>-Objekts muss Service Broker für die verwendete SQL Server-Datenbank aktiviert werden, und Benutzer müssen über Berechtigungen zum Erhalt von Benachrichtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="e2f08-137">Service Broker-Objekte, z. B. Benachrichtigungswarteschlangen, werden vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="e2f08-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="e2f08-138">Außerdem wird vom <xref:System.Data.SqlClient.SqlDependency>-Objekt automatisch ein Arbeitsthread gestartet, um Benachrichtigungen zu verarbeiten, wenn sie zur Warteschlange gesendet werden. Außerdem wird die Service Broker-Meldung analysiert, und die Informationen werden als Ereignisargumentdaten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e2f08-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="e2f08-139">Das <xref:System.Data.SqlClient.SqlDependency>-Objekt muss initialisiert werden, indem die `Start`-Methode aufgerufen wird, um eine Abhängigkeit zur Datenbank festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e2f08-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="e2f08-140">Dies ist eine statische Methode, die nur einmal während der Initialisierung der Anwendung für jede erforderliche Datenbankverbindung aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="e2f08-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="e2f08-141">Für jede Abhängigkeit, die hergestellt wurde, sollte die `Stop`-Methode bei Beenden der Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e2f08-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="e2f08-142">Verwenden von "SqlNotificationRequest"</span><span class="sxs-lookup"><span data-stu-id="e2f08-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="e2f08-143">Im Gegensatz dazu erfordert <xref:System.Data.Sql.SqlNotificationRequest> das eigene Implementieren der gesamten Empfangsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e2f08-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="e2f08-144">Zusätzlich müssen alle unterstützenden Service Broker-Objekte (z. B. die Warteschlange, der Dienst und die von der Warteschlange unterstützen Meldungstypen) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e2f08-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="e2f08-145">Dieser manuelle Ansatz ist nützlich, wenn Ihre Anwendung besondere Benachrichtigungsmeldungen oder ein besonderes Benachrichtigungsverhalten erfordert oder wenn die Anwendung Teil einer größeren Service Broker-Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="e2f08-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f08-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2f08-146">See Also</span></span>  
 [<span data-ttu-id="e2f08-147">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2f08-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="e2f08-148">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e2f08-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
