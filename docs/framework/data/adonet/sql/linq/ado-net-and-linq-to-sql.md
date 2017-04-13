---
title: "ADO.NET und LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ADO.NET und LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Technologiefamilie.  Es basiert auf den vom [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Anbietermodell bereitgestellten Diensten.  Sie können deshalb [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Code mit vorhandenen [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Anwendungen kombinieren und aktuelle [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Lösungen zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] migrieren.  Die folgende Abbildung stellt eine allgemeine Ansicht der Beziehung dar.  
  
 ![LINQ to SQL und ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq\_3")  
  
## Verbindungen  
 Sie können eine vorhandene [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Verbindung angeben, wenn Sie einen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> erstellen.  Alle Operationen mit dem <xref:System.Data.Linq.DataContext> \(einschließlich Abfragen\) verwenden diese bereitgestellte Verbindung.  Ist die Verbindung bereits geöffnet, lässt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sie nach deren Verwendung unverändert.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 Sie können stets auf die Verbindung zugreifen und diese selbst beenden, indem Sie die <xref:System.Data.Linq.DataContext.Connection%2A>\-Eigenschaft wie im folgenden Code verwenden:  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## Transaktionen  
 Sie können Ihren <xref:System.Data.Linq.DataContext> mit Ihrer eigenen Datenbanktransaktion ergänzen, wenn Ihre Anwendung die Transaktion bereits initiiert hat und Sie möchten, dass der <xref:System.Data.Linq.DataContext> berücksichtigt wird.  
  
 Die bevorzugte Methode für Transaktionen mit [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] ist die Verwendung des <xref:System.Transactions.TransactionScope>\-Objekts.  Mithilfe dieses Ansatzes können Sie verteilte Transaktionen erstellen, die über Datenbanken hinweg und in Verbindung mit anderen speicherresidenten Ressourcen\-Managern funktionieren.  Transaktionsbereiche erfordern zunächst wenige Ressourcen.  Sie stufen sich selbst nur dann zu verteilten Transaktionen hoch, wenn mehrere Verbindungen innerhalb des Transaktionsbereichs vorliegen.  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 Sie können diesen Ansatz nicht für alle Datenbanken verwenden.  Beispielsweise kann die SqlClient\-Verbindung keine Systemtransaktionen hochstufen, wenn ein [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]\-Server verwendet wird.  Stattdessen wird automatisch eine vollständige, verteilte Transaktion erzeugt, wenn erkannt wird, dass ein Transaktionsbereich genutzt wird.  
  
## Direkte SQL\-Befehle  
 Es kann zu Situationen kommen, in denen die Möglichkeiten des <xref:System.Data.Linq.DataContext> zum Abfragen oder zum Übergeben von Änderungen für die spezifische Aufgabe nicht ausreichen.  In diesen Fällen können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>\-Methode verwenden, um SQL\-Befehle an die Datenbank zu übergeben und die Abfrageergebnisse in Objekte zu konvertieren.  
  
 Nehmen Sie zum Beispiel an, dass die Daten der `Customer`\-Klasse auf zwei Tabellen \(customer1 und customer2\) verteilt sind.  Die folgende Abfrage gibt eine Sequenz von `Customer`\-Objekten zurück:  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 Sofern die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen, erzeugt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Objekte aus einer SQL\-Abfrage.  
  
### Parameter  
 Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>\-Methode akzeptiert Parameter.  Der folgende Code führt eine parametrisierte Abfrage aus:  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.  `String.Format()` ersetzt die verschachtelten Parameter der angegebenen Abfragezeichenfolge durch generierte Parameternamen, wie z. B. `@p0`, `@p1` …, `@p(n)`.  
  
## Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET\-Befehl und einem DataContext](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)