---
title: Aktivieren von Abfragebenachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 693e67b4d369eb69b8e0a9dded6decb2d3928459
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554878"
---
# <a name="enabling-query-notifications"></a>Aktivieren von Abfragebenachrichtigungen
Anwendungen, die Abfragebenachrichtigungen nutzen, weisen eine Reihe gemeinsamer Anforderungen auf. Ihre Datenquelle muss richtig konfiguriert sein, um SQL-Abfragebenachrichtigungen zu unterstützen, und die Benutzer müssen über die richtigen client- und serverseitigen Berechtigungen verfügen.  
  
 Voraussetzungen für Abfragebenachrichtigungen:  
  
- Aktivieren Sie Abfragebenachrichtigungen für Ihre Datenbank.  
  
- Stellen Sie sicher, dass die Benutzer-ID für das Herstellen der Verbindung mit der Datenbank über die erforderlichen Berechtigungen verfügt.  
  
- Verwenden Sie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, um eine gültige SELECT-Anweisung mit einem zugehörigen Benachrichtigungsobjekt (entweder <xref:System.Data.SqlClient.SqlDependency> oder <xref:System.Data.Sql.SqlNotificationRequest>) auszuführen.  
  
- Geben Sie den Code zur Verarbeitung der Benachrichtigung an, wenn sich die überwachten Daten ändern.  
  
## <a name="query-notifications-requirements"></a>Anforderungen für Abfragebenachrichtigungen  
 Abfragebenachrichtigungen werden nur für SELECT-Anweisungen unterstützt, die eine Liste bestimmter Anforderungen erfüllen. Die folgende Tabelle enthält Links zur Dokumentation zu Service Broker und Abfragebenachrichtigungen in der SQL Server-Onlinedokumentation.  
  
 **SQL Server-Dokumentation**  
  
- [Erstellen einer Abfrage für die Benachrichtigung](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Sicherheitsaspekte für Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Sicherheit und Schutz (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Sicherheitsaspekte für Notification Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Berechtigungen für Abfragebenachrichtigungen](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Internationale Gesichtspunkte bei Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Überlegungen zu Lösungsentwürfen (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Entwicklerhandbuch (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Aktivieren von Abfragebenachrichtigungen für das Ausführen von Beispielcode  
 Führen Sie zum Aktivieren von Service Broker in der **AdventureWorks**-Datenbank mit SQL Server Management Studio die folgende Transact-SQL-Anweisung aus:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Damit die Beispiele von Abfragebenachrichtigungen ordnungsgemäß ausgeführt werden können, müssen auf dem Datenbankserver die folgenden Transact-SQL-Anweisungen ausgeführt werden.  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Berechtigungen für Abfragebenachrichtigungen  
 Benutzer, die Befehle ausführen, für die eine Benachrichtigung gewünscht wird, müssen auf dem Server die Datenbankberechtigung SUBSCRIBE QUERY NOTIFICATIONS haben.  
  
 Clientseitiger Code, der in einer teilweise vertrauenswürdigen Situation ausgeführt wird, erfordert <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 Der folgende Code erstellt ein <xref:System.Data.SqlClient.SqlClientPermission>-Objekt, wobei <xref:System.Security.Permissions.PermissionState> auf <xref:System.Security.Permissions.PermissionState.Unrestricted> festgelegt wird. <xref:System.Security.CodeAccessPermission.Demand%2A> erzwingt zur Laufzeit <xref:System.Security.SecurityException>, wenn allen Aufrufern, die höher im Aufrufstapel stehen, die Berechtigung nicht erteilt wurde.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Auswählen eines Benachrichtigungsobjekts  
 Die Abfragebenachrichtigungs-API stellt zwei Objekte zum Verarbeiten von Benachrichtigungen zur Verfügung: <xref:System.Data.SqlClient.SqlDependency> und <xref:System.Data.Sql.SqlNotificationRequest>. Im Allgemeinen sollten die meisten Nicht-ASP.NET-Anwendungen das <xref:System.Data.SqlClient.SqlDependency>-Objekt verwenden. ASP.NET-Anwendungen sollten die übergeordnete <xref:System.Web.Caching.SqlCacheDependency> verwenden, die die <xref:System.Data.SqlClient.SqlDependency> umschließt und einen Rahmen für die Verwaltung der Benachrichtigungs- und Zwischenspeicherobjekte bietet.  
  
### <a name="using-sqldependency"></a>Verwenden von SqlDependency  
 Zum Verwenden der <xref:System.Data.SqlClient.SqlDependency> muss Service Broker für die verwendete SQL Server-Datenbank aktiviert werden, und Benutzer müssen über Berechtigungen zum Erhalt von Benachrichtigungen verfügen. Service Broker-Objekte, wie z. B. die Benachrichtigungswarteschlange, sind vordefiniert.  
  
 Zusätzlich startet <xref:System.Data.SqlClient.SqlDependency> automatisch einen Arbeitsthread, um Benachrichtigungen in der Reihenfolge zu verarbeiten, in der sie in die Warteschlange gestellt werden. Außerdem wird die Service Broker-Meldung analysiert, und die Informationen werden als Ereignisargumentdaten verfügbar gemacht. <xref:System.Data.SqlClient.SqlDependency> muss durch Aufrufen der `Start`-Methode initialisiert werden, um eine Abhängigkeit zur Datenbank einzurichten. Dies ist eine statische Methode, die nur einmal während der Anwendungsinitialisierung für jede erforderliche Datenbankverbindung aufgerufen werden muss. Die `Stop`-Methode muss beim Beenden der Anwendung für jede Abhängigkeitsverbindung, die hergestellt wurde, aufgerufen werden.  
  
### <a name="using-sqlnotificationrequest"></a>Verwenden von SqlNotificationRequest  
 Im Gegensatz dazu erfordert <xref:System.Data.Sql.SqlNotificationRequest>, dass Sie die gesamte Lauschinfrastruktur selbst implementieren. Darüber hinaus müssen alle unterstützenden Service Broker-Objekte wie Warteschlange, Dienst und von der Warteschlange unterstützte Nachrichtentypen definiert werden. Dieser manuelle Ansatz ist nützlich, wenn Ihre Anwendung spezielle Benachrichtigungsmeldungen oder -verhalten erfordert, oder wenn Ihre Anwendung Teil einer größeren Service Broker-Anwendung ist.  
  
## <a name="see-also"></a>Siehe auch

- [Abfrage Benachrichtigungen in SQL Server](query-notifications-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
