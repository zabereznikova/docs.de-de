---
title: Aktivieren von Abfragebenachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 9919bad113eb11a38ce137a2cbbf6c67bd5b21ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794083"
---
# <a name="enabling-query-notifications"></a>Aktivieren von Abfragebenachrichtigungen
Anwendungen, die Abfragebenachrichtigungen verwenden, haben einige Anforderungen gemeinsam. Ihre Datenquelle muss richtig konfiguriert sein, um SQL-Abfragebenachrichtigungen zu unterstützen, und die Benutzer müssen über die richtigen client- und serverseitigen Berechtigungen verfügen.  
  
 Zum Verwenden von Abfragebenachrichtigungen muss Folgendes erfüllt sein:  
  
- Aktivieren von Abfragebenachrichtigungen für Ihre Datenbank.  
  
- Sicherstellen, dass die zum Verbinden mit der Datenbank verwendete Benutzer-ID über die erforderlichen Berechtigungen verfügt.  
  
- Verwenden eines <xref:System.Data.SqlClient.SqlCommand>-Objekts zum Ausführen einer gültigen SELECT-Anweisung mit einem zugehörigen Benachrichtigungsobjekt, entweder <xref:System.Data.SqlClient.SqlDependency> oder <xref:System.Data.Sql.SqlNotificationRequest>.  
  
- Bereitstellen von Code, um die Benachrichtigung zu verarbeiten, falls sich die überwachten Daten ändern.  
  
## <a name="query-notifications-requirements"></a>Anforderungen für Abfragebenachrichtigungen  
 Abfragebenachrichtigungen werden nur für SELECT-Anweisungen unterstützt, die bestimmte Anforderungen erfüllen. Die folgende Tabelle enthält Links zur SQL Server-Onlinedokumentation zu Service Broker und Abfragebenachrichtigungen.  
  
 **Dokumentation zu SQL Server**  
  
- [Erstellen einer Abfrage für die Benachrichtigung](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Sicherheitsüberlegungen für Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Sicherheit und Schutz (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Sicherheitsüberlegungen für Benachrichtigungsdienste](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Berechtigungen für Abfrage Benachrichtigungen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Internationale Überlegungen zu Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Überlegungen zu Lösungs Entwürfen (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [InfoCenter für Service Broker Entwickler](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Entwicklerhandbuch (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Aktivieren von Abfragebenachrichtigungen für das Ausführen von Beispielcode  
 Führen Sie die folgende Transact-SQL-Anweisung aus, um Service Broker für die **AdventureWorks** -Datenbank mithilfe SQL Server Management Studio zu aktivieren:  
  
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

- [Abfragebenachrichtigungen in SQL Server](query-notifications-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
