---
title: Abfragebenachrichtigungen in SQL Server
description: Erfahren Sie, wie Sie mithilfe von Abfrage Benachrichtigungen Anwendungen Benachrichtigen, wenn sich Daten in einer SQL Server Datenbank geändert haben, z. b. zum Aktualisieren von Anwendungs anzeigen.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 43b496db74f7e6fc9bc9f17d946bf34398b32312
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543984"
---
# <a name="query-notifications-in-sql-server"></a>Abfragebenachrichtigungen in SQL Server
Mit Abfragebenachrichtigungen, die auf der Service Broker-Infrastruktur aufsetzen, können Anwendungen benachrichtigt werden, wenn sich Daten geändert haben. Diese Funktion ist besonders nützlich für Anwendungen, die einen Informationscache aus einer Datenbank zur Verfügung stellen, z. B. eine Webanwendung, und die benachrichtigt werden müssen, wenn die Quelldaten geändert wurden.  
  
 Es gibt drei Möglichkeiten, Abfragebenachrichtigungen mithilfe von ADO.NET zu implementieren:  
  
1. Eine einfache Implementierung wird durch die `SqlNotificationRequest`- zur Verfügung gestellt, die serverseitige Funktionalität verfügbar macht und Ihnen ermöglicht, einen Befehl mit einer Benachrichtigungsanforderung auszuführen.  
  
2. Eine komplexere Implementierung wird von der `SqlDependency`-Klasse bereitgestellt, die eine komplexere Abstraktion der Benachrichtigungsfunktionalität zwischen der Quellanwendung und SQL Server bietet und Ihnen ermöglicht, eine Abhängigkeit zur Erkennung von Änderungen im Server zu nutzen. In den meisten Fällen ist dies die einfachste und effektivste Art, die SQL Server-Benachrichtigungsfunktionen verwalteter Clientanwendungen mithilfe des .NET Framework-Datenanbieters für SQL Server wirkungsvoll zu nutzen.  
  
3. Außerdem können Webanwendungen, die mithilfe von ASP.NET 2.0 oder höher erstellt wurden, die `SqlCacheDependency`-Hilfsklassen verwenden.  
  
 Abfragebenachrichtigungen sind für Anwendungen sinnvoll, die Anzeigen oder Caches als Reaktion auf Änderungen in den zugrunde liegenden Daten aktualisieren müssen. Microsoft SQL Server ermöglicht es .NET Framework-Anwendungen, einen Befehl an SQL Server zu senden und eine Benachrichtigung anzufordern, sobald bei der Ausführung desselben Befehls Resultsets erstellt werden, die sich von den ursprünglich abgerufenen unterscheiden. Auf dem Server generierte Benachrichtigungen werden durch Warteschlangen gesendet, um später verarbeitet zu werden.  
  
 Sie können Benachrichtigungen für SELECT- und EXECUTE-Anweisungen einrichten. Wenn eine EXECUTE-Anweisung verwendet wird, registriert SQL Server eine Benachrichtigung für den ausgeführten Befehl anstelle der EXECUTE-Anweisung selbst. Der Befehl muss den Anforderungen und Einschränkungen für eine SELECT-Anweisung genügen. Wenn ein Befehl, der eine Benachrichtigung registriert, mehrere Anweisungen enthält, erstellt die Datenbank-Engine eine Benachrichtigung für jede Anweisung im Batch.  
  
 Wenn Sie eine Anwendung entwickeln, bei der Sie bei Datenänderungen zuverlässige untergeordnete Benachrichtigungen benötigen, lesen Sie die Abschnitte **Planen einer effizienten Abfrage Benachrichtigungs Strategie** und **Alternativen zum Abfragen von Benachrichtigungen** im Artikel [Planning for Notification (Planen von Benachrichtigungen](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) ). Weitere Informationen zu Abfrage Benachrichtigungen und SQL Server Service Broker finden Sie unter den folgenden Links zu Artikeln in der SQL Server-Dokumentation.  
  
 **SQL Server-Dokumentation**  
  
- [Verwenden von Abfragebenachrichtigungen](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Erstellen einer Abfrage für die Benachrichtigung](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Entwicklung (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Entwicklerhandbuch (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktivieren von Abfrage Benachrichtigungen](enabling-query-notifications.md)  
 Erläutert die Verwendung von Abfragebenachrichtigungen, einschließlich der Anforderungen zu deren Aktivierung und Nutzung.  
  
 [Sqlabhängigkeit in einer ASP.NET-Anwendung](sqldependency-in-an-aspnet-app.md)  
 Zeigt, wie Sie Abfragebenachrichtigungen in einer ASP.NET-Anwendung verwenden können.  
  
 [Erkennen von Änderungen mit sqlabhängigkeit](detecting-changes-with-sqldependency.md)  
 Zeigt, wie Sie ermitteln, ob Abfrageergebnisse von den ursprünglich empfangenen Ergebnissen abweichen.  
  
 [SqlCommand-Ausführung mit "SqlNotificationRequest"](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Veranschaulicht das Konfigurieren eines <xref:System.Data.SqlClient.SqlCommand>-Objekts für dar Arbeiten mit einer Abfragebenachrichtigung.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Beschreibt die <xref:System.Data.Sql.SqlNotificationRequest>-Klasse und alle ihre Member.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Beschreibt die <xref:System.Data.SqlClient.SqlDependency>-Klasse und alle ihre Member.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Beschreibt die <xref:System.Web.Caching.SqlCacheDependency>-Klasse und alle ihre Member.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
