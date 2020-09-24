---
title: Aktivieren von Abfragebenachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 4e9b3a2e1f176a9d01e983bc469cc4032fa5d730
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156172"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="a3e97-102">Aktivieren von Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="a3e97-102">Enabling Query Notifications</span></span>

<span data-ttu-id="a3e97-103">Anwendungen, die Abfragebenachrichtigungen nutzen, weisen eine Reihe gemeinsamer Anforderungen auf.</span><span class="sxs-lookup"><span data-stu-id="a3e97-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="a3e97-104">Ihre Datenquelle muss richtig konfiguriert sein, um SQL-Abfragebenachrichtigungen zu unterstützen, und die Benutzer müssen über die richtigen client- und serverseitigen Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a3e97-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="a3e97-105">Voraussetzungen für Abfragebenachrichtigungen:</span><span class="sxs-lookup"><span data-stu-id="a3e97-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="a3e97-106">Aktivieren Sie Abfragebenachrichtigungen für Ihre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a3e97-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="a3e97-107">Stellen Sie sicher, dass die Benutzer-ID für das Herstellen der Verbindung mit der Datenbank über die erforderlichen Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="a3e97-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="a3e97-108">Verwenden Sie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, um eine gültige SELECT-Anweisung mit einem zugehörigen Benachrichtigungsobjekt (entweder <xref:System.Data.SqlClient.SqlDependency> oder <xref:System.Data.Sql.SqlNotificationRequest>) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3e97-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="a3e97-109">Geben Sie den Code zur Verarbeitung der Benachrichtigung an, wenn sich die überwachten Daten ändern.</span><span class="sxs-lookup"><span data-stu-id="a3e97-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="a3e97-110">Anforderungen für Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="a3e97-110">Query Notifications Requirements</span></span>  

 <span data-ttu-id="a3e97-111">Abfragebenachrichtigungen werden nur für SELECT-Anweisungen unterstützt, die eine Liste bestimmter Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a3e97-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="a3e97-112">Die folgende Tabelle enthält Links zur Dokumentation zu Service Broker und Abfragebenachrichtigungen in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="a3e97-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a3e97-113">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="a3e97-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="a3e97-114">[Erstellen einer Abfrage für die Benachrichtigung](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-114">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="a3e97-115">[Sicherheitsaspekte für Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="a3e97-115">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="a3e97-116">[Sicherheit und Schutz (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-116">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="a3e97-117">[Sicherheitsaspekte für Notification Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="a3e97-117">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="a3e97-118">[Berechtigungen für Abfragebenachrichtigungen](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-118">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="a3e97-119">[Internationale Gesichtspunkte bei Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="a3e97-119">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="a3e97-120">[Überlegungen zu Lösungsentwürfen (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-120">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="a3e97-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="a3e97-122">[Entwicklerhandbuch (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a3e97-122">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="a3e97-123">Aktivieren von Abfragebenachrichtigungen für das Ausführen von Beispielcode</span><span class="sxs-lookup"><span data-stu-id="a3e97-123">Enabling Query Notifications to Run Sample Code</span></span>  

 <span data-ttu-id="a3e97-124">Führen Sie zum Aktivieren von Service Broker in der **AdventureWorks**-Datenbank mit SQL Server Management Studio die folgende Transact-SQL-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="a3e97-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="a3e97-125">Damit die Beispiele von Abfragebenachrichtigungen ordnungsgemäß ausgeführt werden können, müssen auf dem Datenbankserver die folgenden Transact-SQL-Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3e97-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="a3e97-126">Berechtigungen für Abfragebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="a3e97-126">Query Notifications Permissions</span></span>  

 <span data-ttu-id="a3e97-127">Benutzer, die Befehle ausführen, für die eine Benachrichtigung gewünscht wird, müssen auf dem Server die Datenbankberechtigung SUBSCRIBE QUERY NOTIFICATIONS haben.</span><span class="sxs-lookup"><span data-stu-id="a3e97-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="a3e97-128">Clientseitiger Code, der in einer teilweise vertrauenswürdigen Situation ausgeführt wird, erfordert <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="a3e97-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="a3e97-129">Der folgende Code erstellt ein <xref:System.Data.SqlClient.SqlClientPermission>-Objekt, wobei <xref:System.Security.Permissions.PermissionState> auf <xref:System.Security.Permissions.PermissionState.Unrestricted> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e97-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="a3e97-130"><xref:System.Security.CodeAccessPermission.Demand%2A> erzwingt zur Laufzeit <xref:System.Security.SecurityException>, wenn allen Aufrufern, die höher im Aufrufstapel stehen, die Berechtigung nicht erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3e97-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="a3e97-131">Auswählen eines Benachrichtigungsobjekts</span><span class="sxs-lookup"><span data-stu-id="a3e97-131">Choosing a Notification Object</span></span>  

 <span data-ttu-id="a3e97-132">Die Abfragebenachrichtigungs-API stellt zwei Objekte zum Verarbeiten von Benachrichtigungen zur Verfügung: <xref:System.Data.SqlClient.SqlDependency> und <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="a3e97-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="a3e97-133">Im Allgemeinen sollten die meisten Nicht-ASP.NET-Anwendungen das <xref:System.Data.SqlClient.SqlDependency>-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3e97-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="a3e97-134">ASP.NET-Anwendungen sollten die übergeordnete <xref:System.Web.Caching.SqlCacheDependency> verwenden, die die <xref:System.Data.SqlClient.SqlDependency> umschließt und einen Rahmen für die Verwaltung der Benachrichtigungs- und Zwischenspeicherobjekte bietet.</span><span class="sxs-lookup"><span data-stu-id="a3e97-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="a3e97-135">Verwenden von SqlDependency</span><span class="sxs-lookup"><span data-stu-id="a3e97-135">Using SqlDependency</span></span>  

 <span data-ttu-id="a3e97-136">Zum Verwenden der <xref:System.Data.SqlClient.SqlDependency> muss Service Broker für die verwendete SQL Server-Datenbank aktiviert werden, und Benutzer müssen über Berechtigungen zum Erhalt von Benachrichtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a3e97-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="a3e97-137">Service Broker-Objekte, wie z. B. die Benachrichtigungswarteschlange, sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="a3e97-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="a3e97-138">Zusätzlich startet <xref:System.Data.SqlClient.SqlDependency> automatisch einen Arbeitsthread, um Benachrichtigungen in der Reihenfolge zu verarbeiten, in der sie in die Warteschlange gestellt werden. Außerdem wird die Service Broker-Meldung analysiert, und die Informationen werden als Ereignisargumentdaten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a3e97-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="a3e97-139"><xref:System.Data.SqlClient.SqlDependency> muss durch Aufrufen der `Start`-Methode initialisiert werden, um eine Abhängigkeit zur Datenbank einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a3e97-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="a3e97-140">Dies ist eine statische Methode, die nur einmal während der Anwendungsinitialisierung für jede erforderliche Datenbankverbindung aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="a3e97-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="a3e97-141">Die `Stop`-Methode muss beim Beenden der Anwendung für jede Abhängigkeitsverbindung, die hergestellt wurde, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a3e97-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="a3e97-142">Verwenden von SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="a3e97-142">Using SqlNotificationRequest</span></span>  

 <span data-ttu-id="a3e97-143">Im Gegensatz dazu erfordert <xref:System.Data.Sql.SqlNotificationRequest>, dass Sie die gesamte Lauschinfrastruktur selbst implementieren.</span><span class="sxs-lookup"><span data-stu-id="a3e97-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="a3e97-144">Darüber hinaus müssen alle unterstützenden Service Broker-Objekte wie Warteschlange, Dienst und von der Warteschlange unterstützte Nachrichtentypen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3e97-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="a3e97-145">Dieser manuelle Ansatz ist nützlich, wenn Ihre Anwendung spezielle Benachrichtigungsmeldungen oder -verhalten erfordert, oder wenn Ihre Anwendung Teil einer größeren Service Broker-Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="a3e97-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e97-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3e97-146">See also</span></span>

- [<span data-ttu-id="a3e97-147">Abfrage Benachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3e97-147">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="a3e97-148">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3e97-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
