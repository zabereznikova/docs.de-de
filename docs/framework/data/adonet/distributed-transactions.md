---
title: "Verteilte Transaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 718b257c-bcb2-408e-b004-a7b0adb1c176
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Verteilte Transaktionen
Bei einer Transaktion handelt es sich u. a. um mehrere zusammenhängende Aufgaben, die entweder in ihrer Gesamtheit erfolgreich abgeschlossen werden \(Commit\) oder nicht \(Abort\).  Bei einer *verteilten Transaktion* handelt es sich um eine Transaktion, die sich auf verschiedene Ressourcen auswirkt.  Damit ein Commit einer verteilten Transaktion erfolgreich ausgeführt werden kann, müssen alle Beteiligten gewährleisten, dass jede vorgenommene Datenänderung dauerhaft ist.  Änderungen müssen auch im Fall von Systemausfällen oder anderen unvorhergesehenen Ereignissen dauerhaft sein.  Sobald auch nur ein Beteiligter dies nicht gewährleisten kann, kann die gesamte Transaktion nicht ausgeführt werden, und sämtliche im Zuge der Transaktion durchgeführten Datenänderungen werden in einem Rollback zurückgenommen.  
  
> [!NOTE]
>  Wenn Sie versuchen, einen Commit oder Rollback für eine Transaktion auszuführen, wenn ein `DataReader` gestartet wird und die Transaktion aktiv ist, wird eine Ausnahme ausgelöst.  
  
## Arbeiten mit System.Transactions  
 In .NET Framework werden verteilte Transaktionen durch die API im <xref:System.Transactions>\-Namespace verwaltet.  Die <xref:System.Transactions>\-API delegiert die Behandlung verteilter Transaktionen an einen Transaktionsmonitor wie den MS DTC \(Microsoft Distributed Transaction Coordinator\), wenn mehrere ständige Ressourcen\-Manager beteiligt sind.  Weitere Informationen finden Sie unter [Transaction Fundamentals](http://msdn.microsoft.com/de-de/2a476b63-b94f-443f-992d-53943fdf4e5d).  
  
 Die Unterstützung der Auflistung in einer verteilten Transaktion mithilfe der `EnlistTransaction`\-Methode, die eine Verbindung in einer <xref:System.Transactions.Transaction>\-Instanz auflistet, ist eine neue Funktion in ADO.NET 2.0.  In früheren Versionen von ADO.NET wurde die explizite Eintragung in verteilte Transaktionen mithilfe der `EnlistDistributedTransaction`\-Methode einer Verbindung für das Eintragen einer Verbindung in eine <xref:System.EnterpriseServices.ITransaction>\-Instanz durchgeführt, die aus Gründen der Abwärtskompatibilität unterstützt wird.  Weitere Informationen zu Enterprise Services\-Transaktionen finden Sie unter [Interoperability with Enterprise Services and COM\+ Transactions](http://msdn.microsoft.com/de-de/2e93b3c6-4d48-4b9b-82b2-7d5908a2c970).  
  
 Wenn eine <xref:System.Transactions>\-Transaktion mit dem .NET Framework\-Anbieter für SQL Server unter Verwendung einer SQL Server\-Datenbank verwendet wird, wird automatisch eine kompakte <xref:System.Transactions.Transaction> verwendet.  Die Transaktion kann anschließend bei Bedarf zu einer vollständig verteilten Transaktion heraufgestuft werden.  Weitere Informationen finden Sie unter [System.Transactions\-Integration in SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md).  
  
> [!NOTE]
>  Die maximale Anzahl an verteilten Transaktionen, an denen eine Oracle\-Datenbank gleichzeitig teilnehmen kann, liegt standardmäßig bei 10.  Nach der zehnten Transaktion wird, bei Verbindung mit einer Oracle\-Datenbank, eine Ausnahme ausgelöst.  Oracle bietet keine Unterstützung für `DDL` innerhalb einer verteilten Transaktion.  
  
## Automatisches Eintragen in eine verteilte Transaktion  
 Die automatische Eintragung ist die Standard\- \(und bevorzugte\) Methode zum Integrieren von ADO.NET\-Verbindungen in die `System.Transactions`.  Ein Verbindungsobjekt trägt sich automatisch in eine vorhandene verteilte Transaktion ein, wenn es feststellt, dass eine Transaktion aktiv ist. Bei `System.Transaction` bedeutet dies, dass `Transaction.Current` nicht NULL ist.  Die automatische Transaktionseintragung erfolgt beim Öffnen der Verbindung.  Dies erfolgt nicht anschließend, auch wenn ein Befehl innerhalb des Gültigkeitsbereichs einer Transaktion ausgeführt wird.  Die automatische Eintragung in vorhandene Transaktionen kann durch die Angabe von `Enlist=false` als Parameter der Verbindungszeichenfolge für eine <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=fullName> oder von `OLE DB Services=-7` als Parameter der Verbindungszeichenfolge für eine <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A?displayProperty=fullName> deaktiviert werden.  Weitere Informationen zu Oracle\- und ODBC\-Parametern der Verbindungszeichenfolge finden Sie unter der <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A?displayProperty=fullName> oder der <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A?displayProperty=fullName>.  
  
## Manuelles Eintragen in eine verteilte Transaktion  
 Wenn die automatische Eintragung deaktiviert ist oder wenn Sie eine Transaktion eintragen müssen, die nach dem Herstellen der Verbindung begonnen wurde, können Sie eine vorhandene verteilte Transaktion mithilfe der `EnlistTransaction`\-Methode des <xref:System.Data.Common.DbConnection>\-Objekts für den entsprechenden Anbieter eintragen.  Durch das Eintragen in eine vorhandene verteilte Transaktion wird sichergestellt, dass bei einem Commit oder Rollback der Transaktion auch die Änderungen einbezogen werden, die vom Code an der Datenquelle vorgenommen wurden.  
  
 Das Eintragen in verteilte Transaktionen eignet sich besonders beim Pooling von Geschäftsobjekten.  Wenn sich ein Geschäftsobjekt mit einer hergestellten Verbindung in einem Pool befindet, erfolgt die automatische Transaktionseintragung nur, wenn diese Verbindung hergestellt wird.  Wenn mehrere Transaktionen unter Verwendung des Geschäftsobjekts im Pool ausgeführt werden, wird die für das Objekt hergestellte Verbindung nicht automatisch in neu initialisierte Transaktionen eingetragen.  In diesem Fall können Sie die automatische Transaktionseintragung für die Verbindung deaktivieren und die Verbindung mithilfe der `EnlistTransaction`\-Methode in Transaktionen eintragen.  
  
 Die `EnlistTransaction` \-Methode erhält ein einzelnes Argument vom Typ <xref:System.Transactions.Transaction>, das einen Verweis auf die vorhandene Transaktion darstellt.  Nach dem Aufrufen der `EnlistTransaction`\-Methode der Verbindung werden alle Änderungen, die mit der Verbindung an der Datenquelle vorgenommen wurden, in die Transaktion eingetragen.  Beim Übergeben eines NULL\-Werts wird die Verbindung aus der aktuellen verteilten Transaktionseintragung ausgetragen.  Beachten Sie, dass die Verbindung vor dem Aufrufen der `EnlistTransaction`\-Methode hergestellt werden muss.  
  
> [!NOTE]
>  Nachdem eine Verbindung ausdrücklich in eine Transaktion eingetragen wurde, kann sie solange nicht ausgetragen oder in eine andere Transaktion eingetragen werden, bis die erste Transaktion beendet wurde.  
  
> [!CAUTION]
>  Die `EnlistTransaction`\-Methode löst eine Ausnahme aus, wenn die Verbindung bereits mithilfe ihrer <xref:System.Data.Common.DbConnection.BeginTransaction%2A>\-Methode eine Transaktion begonnen hat.  Wenn es sich bei der Transaktion jedoch um eine lokale Transaktion handelt, die an der Datenquelle begonnen wurde \(z. B. die explizite Ausführung der BEGIN TRANSACTION\-ANWEISUNG mithilfe eines <xref:System.Data.SqlClient.SqlCommand>\), führt die `EnlistTransaction`\-Methode einen Rollback der lokalen Transaktion durch und trägt sich selbst wie angefordert in die vorhandene verteilte Transaktion ein.  Sie werden nicht über den Rollback der lokalen Transaktion benachrichtigt und müssen nicht begonnene lokale Transaktionen mithilfe der <xref:System.Data.Common.DbConnection.BeginTransaction%2A>\-Methode verwalten.  Wenn Sie den .NET Framework\-Datenanbieter für SQL Server \(`SqlClient`\) mit SQL Server verwenden, wird beim Eintragen eine Ausnahme ausgelöst.  Alle anderen Fälle bleiben unerkannt.  
  
## Heraufstufbare Transaktionen in SQL Server  
 SQL Server unterstützt heraufstufbare Transaktionen, bei denen eine lokale kompakte Transaktion nur bei Bedarf automatisch zu einer verteilten Transaktion heraufgestuft werden kann.  Eine heraufstufbare Transaktion ruft den zusätzlichen Aufwand einer verteilten Transaktion nur hervor, wenn dieser erforderlich ist.  Weitere Informationen sowie ein Codebeispiel finden Sie unter [System.Transactions\-Integration in SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md).  
  
## Konfigurieren von verteilten Transaktionen  
 Möglicherweise müssen Sie MS DTC über das Netzwerk aktivieren, um verteilte Transaktionen zu verwenden.  Wenn die Windows\-Firewall aktiviert ist, müssen Sie dem MS DTC\-Dienst die Erlaubnis erteilen, das Netzwerk zu verwenden, oder den MS DTC\-Port öffnen.  
  
## Siehe auch  
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [System.Transactions\-Integration in SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)