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
# <a name="query-notifications-in-sql-server"></a>Abfragebenachrichtigungen in SQL Server
Mit Abfragebenachrichtigungen, die auf der Service Broker-Infrastruktur aufsetzen, können Anwendungen benachrichtigt werden, wenn sich Daten geändert haben. Diese Funktion ist besonders nützlich bei Anwendungen, die Informationen aus einer Datenbank zwischenspeichern, z. B. aus einer Webanwendung, und bei Änderungen von Quelldaten benachrichtigt werden müssen.  
  
 Mithilfe von ADO.NET können Abfragebenachrichtigungen auf dreierlei Weise implementiert werden:  
  
1.  Die konkrete Implementierung wird von der `SqlNotificationRequest`-Klasse bereitgestellt, die serverseitige Funktionen verfügbar macht und das Ausführen von Befehlen mit einer Benachrichtigungsanforderung ermöglicht.  
  
2.  Für die übergeordnete Implementierung ist die `SqlDependency`-Klasse zuständig. Diese Klasse stellt eine allgemeine Abstraktion der Benachrichtigungsfunktionalität zwischen der Quellanwendung und SQL Server bereit, die die Verwendung einer Abhängigkeit ermöglicht, um Änderungen im Server zu erkennen. In den meisten Fällen ist dies die einfachste und effektivste Art, die SQL Server-Benachrichtigungsfunktionen verwalteter Clientanwendungen mithilfe des .NET Framework-Datenanbieters für SQL Server wirkungsvoll zu nutzen.  
  
3.  Außerdem können Webanwendungen, die mithilfe von ASP.NET 2.0 oder höher erstellt wurden, die `SqlCacheDependency`-Hilfsklassen verwenden.  
  
 Abfragebenachrichtigungen werden für Anwendungen verwendet, die Anzeigen oder Zwischenspeicherungen als Antwort auf Änderungen in den zugrunde liegenden Daten aktualisieren müssen. Microsoft SQL Server ermöglicht es .NET Framework-Anwendungen, einen Befehl an SQL Server zu senden und eine Benachrichtigung anzufordern, sobald bei der Ausführung desselben Befehls Resultsets erstellt werden, die sich von den ursprünglich abgerufenen unterscheiden. Auf dem Server generierte Benachrichtigungen werden durch Warteschlangen gesendet, um später verarbeitet zu werden.  
  
 Benachrichtigungen können für SELECT- und für EXECUTE-Anweisungen eingerichtet werden. Bei Verwendung einer EXECUTE-Anweisung registriert SQL Server eine Benachrichtigung für den ausgeführten Befehl und nicht für die EXECUTE-Anweisung selbst. Der Befehl muss den Anforderungen und Einschränkungen einer SELECT-Anweisung gerecht werden. Wenn ein Befehl, der eine Benachrichtigung registriert, mehr als eine Anweisung enthält, erstellt das Datenbankmodul für jede Anweisung im Stapel eine Benachrichtigung.  
  
 Wenn Sie eine Anwendung entwickeln, benötigen Sie zuverlässige Sekunde Benachrichtigungen bei datenänderungen, lesen Sie die Abschnitte **Planen einer effizienten Abfragebenachrichtigungs-Strategie** und **Alternativen zur Abfrage Benachrichtigungen** in der [Planen von Benachrichtigungen](http://go.microsoft.com/fwlink/?LinkId=211984) in SQL Server-Onlinedokumentation. Weitere Informationen zu Abfragebenachrichtigungen und SQL Server Service Broker finden Sie unter den folgenden Links zu Themen in der SQL Server-Onlinedokumentation.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
-   [Verwenden von Abfragebenachrichtigungen](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [Erstellen eine Abfrage für die Benachrichtigung](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [Service Broker](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [Service Broker-Entwickler (InfoCenter)](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [Entwicklung (Service Broker)](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktivieren von Abfragebenachrichtigungen](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 Erläutert die Verwendung von Abfragebenachrichtigungen und informiert über die Anforderungen, die für deren Aktivierung und Verwendung erfüllt sein müssen.  
  
 ["SqlDependency" in einer ASP.NET-Anwendung](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 Zeigt, wie Sie Abfragebenachrichtigungen von einer ASP.NET-Anwendung aus verwenden können.  
  
 [Erkennen von Änderungen mit "SqlDependency"](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 Zeigt, wie Sie erkennen können, dass sich Abfrageergebnisse von den ursprünglich empfangenen Abfrageergebnissen unterscheiden.  
  
 ["SqlCommand"-Ausführung mit "SqlNotificationRequest"](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Zeigt, wie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt so konfiguriert werden kann, dass es mit einer Abfragebenachrichtigung arbeitet.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Beschreibt die <xref:System.Data.Sql.SqlNotificationRequest>-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Beschreibt die <xref:System.Data.SqlClient.SqlDependency>-Klasse und alle Member dieser Klasse.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Beschreibt die <xref:System.Web.Caching.SqlCacheDependency>-Klasse und alle Member dieser Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
