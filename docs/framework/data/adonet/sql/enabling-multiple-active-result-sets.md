---
title: Aktivieren von Multiple Active Result Sets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
ms.openlocfilehash: 073cd3a57f254f639fac44900ff6bf022e1fb165
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504305"
---
# <a name="enabling-multiple-active-result-sets"></a>Aktivieren von Multiple Active Result Sets
MARS (Multiple Active Result Sets) ist eine Funktion, die mit SQL Server verwendet wird und das Ausführen mehrerer Batches über eine einzelne Verbindung ermöglicht. Wenn MARS für die Verwendung mit SQL Server aktiviert wird, fügen die einzelnen verwendeten Befehlsobjekte der Verbindung eine Sitzung hinzu.  
  
> [!NOTE]
>  Eine einzelne MARS-Sitzung öffnet genau eine logische Verbindung zur Verwendung durch MARS und dann jeweils eine logische Verbindung pro aktiven Befehl.  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a>Aktivieren und Deaktivieren von MARS in der Verbindungszeichenfolge  
  
> [!NOTE]
>  Die folgenden Verbindungszeichenfolgen verwenden Sie das Beispiel **AdventureWorks** Datenbank in SQL Server enthalten. Bei den bereitgestellten Verbindungszeichenfolgen wird davon ausgegangen, dass die Datenbank auf einem Server mit dem Namen "MSSQL1" installiert ist. Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.  
  
 Die MARS-Funktion ist in der Standardeinstellung deaktiviert. Es kann durch Hinzufügen des Schlüsselwortpaars "MultipleActiveResultSets=True" zur Verbindungszeichenfolge aktiviert werden. "True" ist der einzige gültige Wert zum Aktivieren von MARS. Im folgenden Beispiel wird veranschaulicht, wie eine Verbindung mit einer Instanz von SQL Server hergestellt wird und wie angegeben wird, dass MARS aktiviert werden soll.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 MARS kann durch Hinzufügen des Schlüsselwortpaars "MultipleActiveResultSets=False" zur Verbindungszeichenfolge deaktiviert werden. "False" ist der einzige gültige Wert zum Deaktivieren von MARS. In der folgenden Verbindungszeichenfolge wird die Deaktivierung von MARS veranschaulicht.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a>Besondere Überlegungen bei der Verwendung von MARS  
 Im Allgemeinen sollten vorhandene Anwendungen für die Verwendung einer MARS-aktivierten Verbindung keine Änderungen erfordern. Wenn Sie in den Anwendungen jedoch MARS-Funktionen verwenden möchten, sollten Sie die folgenden Besonderheiten berücksichtigen.  
  
### <a name="statement-interleaving"></a>Überlappen von Anweisungen  
 MARS-Vorgänge werden auf dem Server synchron ausgeführt. Die Überlappung der SELECT-Anweisung und der BULK INSERT-Anweisung ist zulässig. Die Anweisungen der Datenbearbeitungssprache (Data Manipulation Language, DML) und der Datendefinitionssprache (Data Definition Language, DDL) werden atomar ausgeführt. Alle Statements, die während der Ausführung eines atomaren Batches ausgeführt werden sollen, werden blockiert. Bei der Parallelausführung auf dem Server handelt es sich nicht um eine MARS-Funktion.  
  
 Wenn zwei Batches mithilfe einer MARS-Verbindung übertragen werden, von denen einer eine SELECT-Anweisung und einer eine DML-Anweisung enthält, kann die DML-Anweisung während der Ausführung der SELECT-Anweisung ausgeführt werden. Die DML-Anweisung muss jedoch vollständig ausgeführt werden, damit die SELECT-Anweisung fortgesetzt werden kann. Wenn beide Anweisungen in derselben Transaktion ausgeführt werden, sind Änderungen, die nach dem Starten der Ausführung der SELECT-Anweisung vorgenommen wurden, für den Lesevorgang nicht sichtbar.  
  
 Eine WAITFOR-Anweisung in einer SELECT-Anweisung wird nicht an die Transaktion übergeben, während diese wartet, d. h., bis die erste Zeile erstellt wurde. Dies bedeutet, dass während des Wartens der WAITFOR-Anweisung keine anderen Batches in derselben Verbindung ausgeführt werden können.  
  
### <a name="mars-session-cache"></a>MARS-Sitzungscache  
 Wenn eine Verbindung mit aktiviertem MARS offen ist, wird eine logische Sitzung erstellt, die zusätzlichen Mehraufwand erfordert. Um den Mehraufwand zu minimieren und Verbessern der Leistung, **SqlClient** speichert die MARS-Sitzung in einer Verbindung. Der Cache kann maximal 10 MARS-Sitzungen enthalten. Dieser Wert kann nicht vom Benutzer geändert werden. Wenn die maximale Sitzungsanzahl erreicht ist und eine neue Sitzung erstellt wird, wird kein Fehler generiert. Der Cache und die darin enthaltenen Sitzungen richten sich jeweils nach der Verbindung. Sie werden nicht von mehreren Verbindungen gemeinsam genutzt. Wenn eine Sitzung freigegeben wird, wird sie an den Pool zurückgegeben, sofern die obere Grenze des Pools erreicht wurde. Wenn der Cachepool voll ist, wird die Sitzung beendet. Die Gültigkeit von MARS-Sitzungen läuft nicht ab. Sie werden lediglich bereinigt, wenn das Verbindungsobjekt freigegeben wird. Der Cache der MARS-Sitzung wird nicht vorab geladen. Dies erfolgt, wenn die Anwendung weitere Sitzungen benötigt.  
  
### <a name="thread-safety"></a>Threadsicherheit  
 MARS-Vorgänge sind nicht threadsicher.  
  
### <a name="connection-pooling"></a>Verbindungspooling  
 MARS-aktivierte Verbindungen werden genau wie andere Verbindungen in einem Pool zusammengefasst. Wenn eine Anwendung zwei Verbindungen öffnet, wobei MARS bei einer aktiviert ist und bei der anderen deaktiviert ist, befinden sich die beiden Verbindungen in separaten Pools. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
### <a name="sql-server-batch-execution-environment"></a>SQL Server-Batchausführungsumgebung  
 Beim Öffnen einer Verbindung wird eine Standardumgebung definiert. Diese Umgebung wird anschließend in eine logische MARS-Sitzung kopiert.  
  
 Die Batchausführungsumgebung enthält die folgenden Komponenten:  
  
-   Gruppenoptionen (z. B. ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)  
  
-   Sicherheitskontext (Benutzerrolle/Anwendungsrolle)  
  
-   Datenbankkontext (aktuelle Datenbank)  
  
-   Ausführungszustandsvariablen (z. B. @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)  
  
-   Temporäre Tabellen auf oberster Ebene  
  
 Mit MARS wird einer Verbindung eine Standardausführungsumgebung zugeordnet. Jeder neue Batch, der mit einer angegebenen Verbindung ausgeführt wird, erhält eine Kopie der Standardumgebung. Bei jeder Ausführung von Code unter einem angegebenen Batch beschränken sich alle an der Umgebung vorgenommenen Änderungen auf den bestimmten Batch. Nachdem die Ausführung beendet ist, werden die Ausführungseinstellungen in die Standardumgebung kopiert. Bei einem einzelnen Batch, der verschiedene nacheinander mit derselben Verbindung auszuführende Befehle ausgibt, entspricht die Semantik genau derjenigen, die von Verbindungen unter Einbeziehung früherer Clients oder Server verfügbar gemacht wird.  
  
### <a name="parallel-execution"></a>Parallelausführung  
 MARS wurde nicht entwickelt, um alle Anforderungen für mehrere Verbindungen in einer Anwendung zu entfernen. Wenn eine Anwendung eine tatsächliche Parallelausführung von Befehlen für einen Server erfordert, sollten mehrere Verbindungen verwendet werden.  
  
 Betrachten Sie beispielsweise das folgende Szenario: Es werden zwei Befehlsobjekte erstellt, wobei ein Objekt zum Verarbeiten eines Resultsets und das andere Objekt zum Aktualisieren von Daten verwendet wird. Diese verwenden eine gemeinsame Verbindung über MARS. In diesem Szenario die `Transaction`.`Commit` das Update schlägt fehl, bis alle Ergebnisse auf der ersten Befehlsobjekts die folgende Ausnahme gelesen wurden:  
  
 Die Nachricht gibt an, dass der Transaktionskontext von einer anderen Sitzung verwendet wird.  
  
 Quelle: .Net SqlClient Data Provider  
  
 Erwartet: (NULL)  
  
 Empfangen: System.Data.SqlClient.SqlException  
  
 Zum Behandeln dieses Szenarien bestehen drei Möglichkeiten:  
  
1.  Starten Sie die Transaktion, nachdem der Reader erstellt wurde, damit dieser keinen Bestandteil der Transaktion darstellt. Jedes Update wird zu einer eigenen Transaktion.  
  
2.  Führen Sie alle Aufgaben aus, nachdem der Reader geschlossen wurde. Dadurch kann eine Vielzahl von Updates entstehen.  
  
3.  Verwenden Sie nicht MARS, sondern für jedes Befehlsobjekt eine separate Verbindung (wie vor der Verwendung von MARS).  
  
### <a name="detecting-mars-support"></a>Ermitteln der MARS-Unterstützung  
 Durch Lesen des `SqlConnection.ServerVersion`-Werts kann eine Anwendung überprüfen, ob MARS unterstützt wird. Der Hauptwert sollte 9 für SQL Server 2005 und 10 für SQL Server 2008 lauten.  
  
## <a name="see-also"></a>Siehe auch  
 [Multiple Active Result Sets (MARS)](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
