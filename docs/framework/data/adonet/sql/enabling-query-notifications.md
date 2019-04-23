---
title: Aktivieren von Abfragebenachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: a2227b33c7caacdd04c7bf50082bb0cfab7f3302
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113944"
---
# <a name="enabling-query-notifications"></a>Aktivieren von Abfragebenachrichtigungen
Anwendungen, die Abfragebenachrichtigungen verwenden, haben einige Anforderungen gemeinsam. Ihre Datenquelle muss richtig konfiguriert sein, um SQL-Abfragebenachrichtigungen zu unterstützen, und die Benutzer müssen über die richtigen client- und serverseitigen Berechtigungen verfügen.  
  
 Zum Verwenden von Abfragebenachrichtigungen muss Folgendes erfüllt sein:  
  
-   Aktivieren von Abfragebenachrichtigungen für Ihre Datenbank.  
  
-   Sicherstellen, dass die zum Verbinden mit der Datenbank verwendete Benutzer-ID über die erforderlichen Berechtigungen verfügt.  
  
-   Verwenden eines <xref:System.Data.SqlClient.SqlCommand>-Objekts zum Ausführen einer gültigen SELECT-Anweisung mit einem zugehörigen Benachrichtigungsobjekt, entweder <xref:System.Data.SqlClient.SqlDependency> oder <xref:System.Data.Sql.SqlNotificationRequest>.  
  
-   Bereitstellen von Code, um die Benachrichtigung zu verarbeiten, falls sich die überwachten Daten ändern.  
  
## <a name="query-notifications-requirements"></a>Anforderungen für Abfragebenachrichtigungen  
 Abfragebenachrichtigungen werden nur für SELECT-Anweisungen unterstützt, die bestimmte Anforderungen erfüllen. Die folgende Tabelle enthält Links zur SQL Server-Onlinedokumentation zu Service Broker und Abfragebenachrichtigungen.  
  
 **SQL Server-Dokumentation**  
  
-   [Erstellen eine Abfrage für die Benachrichtigung](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
-   [Überlegungen zur Sicherheit für Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
-   [Sicherheit und Schutz (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
-   [Sicherheitsaspekte für Notification Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
-   [Berechtigungen für Abfragebenachrichtigungen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
-   [Internationale Gesichtspunkte bei Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
-   [Überlegungen zu Lösungsentwürfen (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
-   [Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
-   [Entwicklerhandbuch (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Aktivieren von Abfragebenachrichtigungen für das Ausführen von Beispielcode  
 Zum Aktivieren von Service Broker für die **AdventureWorks** -Datenbank mithilfe des SQL Server Management Studio, führen Sie die folgende Transact-SQL-Anweisung:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Damit die Abfragebenachrichtigungsbeispiele ordnungsgemäß ausgeführt werden, müssen auf dem Datenbankserver die folgenden Transact-SQL-Anweisungen ausgeführt werden:  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Berechtigungen für Abfragebenachrichtigungen  
 Benutzer, die Befehle ausführen, mit denen Benachrichtigung angefordert werden, müssen über eine SUBSCRIBE QUERY NOTIFICATIONS-Datenbankberechtigung auf dem Server verfügen.  
  
 Clientseitiger Code, der in einem teilweise vertrauenswürdigen Kontext ausgeführt wird, erfordert die <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 Im folgenden Code wird ein <xref:System.Data.SqlClient.SqlClientPermission>-Objekt erstellt, das den <xref:System.Security.Permissions.PermissionState> auf <xref:System.Security.Permissions.PermissionState.Unrestricted> setzt. Die <xref:System.Security.CodeAccessPermission.Demand%2A> erzwingt zur Laufzeit eine <xref:System.Security.SecurityException>, wenn nicht allen Aufrufern, die sich in der Aufrufliste darüber befinden, die Berechtigung gewährt wurde.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Auswählen eines Benachrichtigungsobjekts  
 Die Abfragebenachrichtigungs-API stellt zwei Objekte zum Verarbeiten von Benachrichtigungen zur Verfügung: <xref:System.Data.SqlClient.SqlDependency> und <xref:System.Data.Sql.SqlNotificationRequest>. Im Allgemeinen sollten die meisten Nicht-ASP.NET-Anwendungen das <xref:System.Data.SqlClient.SqlDependency>-Objekt verwenden. ASP.NET-Anwendungen sollten die übergeordnete <xref:System.Web.Caching.SqlCacheDependency> verwenden, die die <xref:System.Data.SqlClient.SqlDependency> umschließt und einen Rahmen für die Verwaltung der Benachrichtigungs- und Zwischenspeicherobjekte bietet.  
  
### <a name="using-sqldependency"></a>Verwenden von "SqlDependency"  
 Zum Verwenden des <xref:System.Data.SqlClient.SqlDependency>-Objekts muss Service Broker für die verwendete SQL Server-Datenbank aktiviert werden, und Benutzer müssen über Berechtigungen zum Erhalt von Benachrichtigungen verfügen. Service Broker-Objekte, z. B. Benachrichtigungswarteschlangen, werden vordefiniert.  
  
 Außerdem wird vom <xref:System.Data.SqlClient.SqlDependency>-Objekt automatisch ein Arbeitsthread gestartet, um Benachrichtigungen zu verarbeiten, wenn sie zur Warteschlange gesendet werden. Außerdem wird die Service Broker-Meldung analysiert, und die Informationen werden als Ereignisargumentdaten verfügbar gemacht. Das <xref:System.Data.SqlClient.SqlDependency>-Objekt muss initialisiert werden, indem die `Start`-Methode aufgerufen wird, um eine Abhängigkeit zur Datenbank festzulegen. Dies ist eine statische Methode, die nur einmal während der Initialisierung der Anwendung für jede erforderliche Datenbankverbindung aufgerufen werden muss. Für jede Abhängigkeit, die hergestellt wurde, sollte die `Stop`-Methode bei Beenden der Anwendung aufgerufen werden.  
  
### <a name="using-sqlnotificationrequest"></a>Verwenden von "SqlNotificationRequest"  
 Im Gegensatz dazu erfordert <xref:System.Data.Sql.SqlNotificationRequest> das eigene Implementieren der gesamten Empfangsinfrastruktur. Zusätzlich müssen alle unterstützenden Service Broker-Objekte (z. B. die Warteschlange, der Dienst und die von der Warteschlange unterstützen Meldungstypen) definiert werden. Dieser manuelle Ansatz ist nützlich, wenn Ihre Anwendung besondere Benachrichtigungsmeldungen oder ein besonderes Benachrichtigungsverhalten erfordert oder wenn die Anwendung Teil einer größeren Service Broker-Anwendung ist.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebenachrichtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
