---
title: Abfragebenachrichtigungen in SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: e31a733635cf56a9c5e539dfb1d71d7d7037175a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645980"
---
# <a name="query-notifications-in-sql-server"></a>Abfragebenachrichtigungen in SQL Server
Mit Abfragebenachrichtigungen, die auf der Service Broker-Infrastruktur aufsetzen, können Anwendungen benachrichtigt werden, wenn sich Daten geändert haben. Diese Funktion ist besonders nützlich bei Anwendungen, die Informationen aus einer Datenbank zwischenspeichern, z. B. aus einer Webanwendung, und bei Änderungen von Quelldaten benachrichtigt werden müssen.  
  
 Mithilfe von ADO.NET können Abfragebenachrichtigungen auf dreierlei Weise implementiert werden:  
  
1. Die konkrete Implementierung wird von der `SqlNotificationRequest`-Klasse bereitgestellt, die serverseitige Funktionen verfügbar macht und das Ausführen von Befehlen mit einer Benachrichtigungsanforderung ermöglicht.  
  
2. Für die übergeordnete Implementierung ist die `SqlDependency`-Klasse zuständig. Diese Klasse stellt eine allgemeine Abstraktion der Benachrichtigungsfunktionalität zwischen der Quellanwendung und SQL Server bereit, die die Verwendung einer Abhängigkeit ermöglicht, um Änderungen im Server zu erkennen. In den meisten Fällen ist dies die einfachste und effektivste Art, die SQL Server-Benachrichtigungsfunktionen verwalteter Clientanwendungen mithilfe des .NET Framework-Datenanbieters für SQL Server wirkungsvoll zu nutzen.  
  
3. Außerdem können Webanwendungen, die mithilfe von ASP.NET 2.0 oder höher erstellt wurden, die `SqlCacheDependency`-Hilfsklassen verwenden.  
  
 Abfragebenachrichtigungen werden für Anwendungen verwendet, die Anzeigen oder Zwischenspeicherungen als Antwort auf Änderungen in den zugrunde liegenden Daten aktualisieren müssen. Microsoft SQL Server ermöglicht es .NET Framework-Anwendungen, einen Befehl an SQL Server zu senden und eine Benachrichtigung anzufordern, sobald bei der Ausführung desselben Befehls Resultsets erstellt werden, die sich von den ursprünglich abgerufenen unterscheiden. Auf dem Server generierte Benachrichtigungen werden durch Warteschlangen gesendet, um später verarbeitet zu werden.  
  
 Benachrichtigungen können für SELECT- und für EXECUTE-Anweisungen eingerichtet werden. Bei Verwendung einer EXECUTE-Anweisung registriert SQL Server eine Benachrichtigung für den ausgeführten Befehl und nicht für die EXECUTE-Anweisung selbst. Der Befehl muss den Anforderungen und Einschränkungen einer SELECT-Anweisung gerecht werden. Wenn ein Befehl, der eine Benachrichtigung registriert, mehr als eine Anweisung enthält, erstellt die Datenbank-Engine für jede Anweisung im Stapel eine Benachrichtigung.  
  
 Wenn Sie eine Anwendung entwickeln, benötigen Sie Sekunde Benachrichtigungen bei datenänderungen, lesen Sie die Abschnitte **Planen einer effizienten Abfragebenachrichtigungs-Strategie** und **Alternativen zur Abfrage Benachrichtigungen** in die [Planen von Benachrichtigungen](https://go.microsoft.com/fwlink/?LinkId=211984) in SQL Server-Onlinedokumentation. Weitere Informationen zu Abfragebenachrichtigungen und SQL Server Service Broker finden Sie unter den folgenden Links zu Themen in der SQL Server-Onlinedokumentation.  
  
 **SQL Server-Dokumentation**  
  
- [Verwenden von Abfragebenachrichtigungen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Erstellen eine Abfrage für die Benachrichtigung](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Entwicklung (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Entwicklerhandbuch (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktivieren von Abfragebenachrichtigungen](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 Erläutert die Verwendung von Abfragebenachrichtigungen und informiert über die Anforderungen, die für deren Aktivierung und Verwendung erfüllt sein müssen.  
  
 [SqlDependency in einer ASP.NET-Anwendung](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 Zeigt, wie Sie Abfragebenachrichtigungen von einer ASP.NET-Anwendung aus verwenden können.  
  
 [Ermitteln von Änderungen mit SqlDependency](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 Zeigt, wie Sie erkennen können, dass sich Abfrageergebnisse von den ursprünglich empfangenen Abfrageergebnissen unterscheiden.  
  
 [SqlCommand-Ausführung mit SqlNotificationRequest](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Zeigt, wie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt so konfiguriert werden kann, dass es mit einer Abfragebenachrichtigung arbeitet.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Beschreibt die <xref:System.Data.Sql.SqlNotificationRequest>-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Beschreibt die <xref:System.Data.SqlClient.SqlDependency>-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Beschreibt die <xref:System.Web.Caching.SqlCacheDependency>-Klasse und alle Member dieser Klasse.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
