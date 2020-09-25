---
title: Lokale Transaktionen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
ms.openlocfilehash: a0b713ab0b81cb2f0661212dae22db34b7f9f3ae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175394"
---
# <a name="local-transactions"></a>Lokale Transaktionen

Transaktionen werden in ADO.NET verwendet, wenn mehrere Aufgaben miteinander verbunden werden sollen, damit sie als eine einzige Verarbeitungseinheit ausgeführt werden können. Stellen Sie sich z.&#160;B. vor, dass eine Anwendung zwei Aufgaben ausführt. Zum einen aktualisiert sie eine Tabelle mit Bestellinformationen. Zum anderen aktualisiert sie eine Tabelle mit Bestandsinformationen und bucht die bestellten Artikel ab. Wenn eine der beiden Aufgaben fehlschlägt, wird für beide Updates ein Rollback ausgeführt.  
  
## <a name="determining-the-transaction-type"></a>Bestimmen des Transaktionstyps  

 Eine Transaktion wird als lokale Transaktion betrachtet, wenn es sich um eine Einphasentransaktion handelt, die von der Datenbank direkt verarbeitet wird. Eine Transaktion wird als verteilte Transaktion betrachtet, wenn Sie durch einen Transaktions Monitor koordiniert wird und ausfallsichere Mechanismen (z. b. Zweiphasencommit) für die Transaktions Auflösung verwendet.  
  
 Die einzelnen .NET Framework-Datenanbieter verfügen jeweils über ein eigenes `Transaction`-Objekt für das Ausführen lokaler Transaktionen. Wählen Sie eine <xref:System.Data.SqlClient>-Transaktion, wenn eine Transaktion in einer SQL Server-Datenbank ausgeführt werden muss. Verwenden Sie für eine Oracle-Transaktion den <xref:System.Data.OracleClient>-Anbieter. Außerdem gibt es eine- <xref:System.Data.Common.DbTransaction> Klasse, die zum Schreiben von Anbieter unabhängigem Code verfügbar ist, der Transaktionen erfordert.  
  
> [!NOTE]
> Transaktionen sind am effizientesten, wenn Sie auf dem Server ausgeführt werden. Wenn Sie mit einer SQL Server-Datenbank arbeiten, die häufig explizite Transaktionen verwendet, empfiehlt es sich, die Transaktionen unter Verwendung der BEGIN TRANSACTION-Anweisung von Transact-SQL als gespeicherte Prozeduren zu schreiben.
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Ausführen einer Transaktion unter Verwendung einer einzelnen Verbindung  

 In ADO.NET können Sie Transaktionen mit dem `Connection`-Objekt steuern. Zum Initiieren einer lokalen Transaktion steht Ihnen die `BeginTransaction`-Methode zur Verfügung. Nachdem Sie eine Transaktion gestartet haben, können Sie mit der `Transaction`-Eigenschaft eines `Command`-Objekts einen Befehl in dieser Transaktion eintragen. Dann können Sie für Änderungen an der Datenquelle auf Grundlage des Erfolgs oder Fehlschlags der Komponenten der Transaktion einen Commit oder Rollback ausführen.  
  
> [!NOTE]
> Die `EnlistDistributedTransaction`-Methode darf nicht für eine lokale Transaktion verwendet werden.  
  
 Der Gültigkeitsbereich der Transaktion ist auf die Verbindung beschränkt. Im folgenden Beispiel wird eine explizite Transaktion ausgeführt, die aus zwei separaten Befehlen im `try`-Block besteht. Die Befehle führen INSERT-Anweisungen für die Production. ScrapReason-Tabelle in der AdventureWorks-SQL Server-Beispieldatenbank aus, für die ein Commit ausgeführt wird, wenn keine Ausnahmen ausgelöst werden. Der Code im `catch`-Block führt ein Rollback der Transaktion aus, wenn eine Ausnahme ausgelöst wird. Wenn die Transaktion abgebrochen oder die Verbindung geschlossen wird, bevor die Transaktion beendet wurde, wird automatisch ein Rollback für die Transaktion ausgeführt.  
  
## <a name="example"></a>Beispiel  

 Führen Sie diese Schritte aus, um eine Transaktion auszuführen:  
  
1. Rufen Sie die <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts auf, um den Start der Transaktion festzulegen. Die <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A>-Methode gibt einen Verweis auf die Transaktion zurück. Dieser Verweis wird den <xref:System.Data.SqlClient.SqlCommand>-Objekten zugeordnet, die in der Transaktion eingetragen sind.  
  
2. Weisen Sie das `Transaction`-Objekt der <xref:System.Data.SqlClient.SqlCommand.Transaction%2A>-Eigenschaft des auszuführenden <xref:System.Data.SqlClient.SqlCommand> zu. Wenn ein Befehl für eine Verbindung mit einer aktiven Transaktion ausgeführt wird und das `Transaction`-Objekt nicht der `Transaction`-Eigenschaft des `Command`-Objekts zugewiesen wurde, wird eine Ausnahme ausgelöst.  
  
3. Führen Sie die erforderlichen Befehle aus.  
  
4. Rufen Sie die <xref:System.Data.SqlClient.SqlTransaction.Commit%2A>-Methode des <xref:System.Data.SqlClient.SqlTransaction>-Objekts auf, um die Transaktion abzuschließen, oder rufen Sie die <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>-Methode auf, um die Transaktion zu beenden. Wenn die Verbindung vor dem Ausführen der <xref:System.Data.SqlClient.SqlTransaction.Commit%2A>-Methode oder der <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>-Methode geschlossen oder verworfen wurde, wird für die Transaktion ein Rollback ausgeführt.  
  
 Im folgenden Codebeispiel wird die Transaktionslogik unter Verwendung von ADO.NET mit Microsoft SQL Server veranschaulicht.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Transaktionen und Parallelität](transactions-and-concurrency.md)
- [Distributed Transactions](distributed-transactions.md) (Verteilte Transaktionen)
- [System.Transactions-Integration in SQL Server](system-transactions-integration-with-sql-server.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
