---
title: Momentaufnahmenisolation in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43ae5dd3-50f5-43a8-8d01-e37a61664176
ms.openlocfilehash: 52c5dba1a21b0e8d8e5af1dc159941e5f4b4aa5f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45970071"
---
# <a name="snapshot-isolation-in-sql-server"></a>Momentaufnahmenisolation in SQL Server
Die Momentaufnahmeisolation erweitert die Parallelität für OLTP-Anwendungen.  
  
## <a name="understanding-snapshot-isolation-and-row-versioning"></a>Informationen zur Snapshot-Isolation und Zeilenversionserstellung  
 Sobald die Snapshot-Isolation aktiviert ist, werden aktuelle Zeilenversionen für jede Transaktion in verwaltet **Tempdb**. Jede Transaktion wird durch eine Transaktionsfolgenummer gekennzeichnet, und diese eindeutigen Nummern werden für jede Zeilenversion aufgezeichnet. Für die Transaktion werden die aktuellsten Zeilenversionen verwendet, die über eine Folgenummer verfügen, die niedriger ist als diejenige der Transaktion. Aktuellere, nach dem Beginn der Transaktion erstellte Zeilenversionen werden von der Transaktion ignoriert.  
  
 Die Benennung "Momentaufnahme" gibt die Tatsache wieder, dass alle Abfragen in der Transaktion auf dieselbe Version (Momentaufnahme) der Datenbank zurückgehen, die auf dem Zustand der Datenbank zum Zeitpunkt des Beginns der Transaktion basiert. In einer Snapshot-Transaktion werden für die zugrunde liegenden Datenzeilen oder Datenseiten keine Sperren bezogen, wodurch andere Transaktionen ausgeführt werden können, ohne durch eine vorherige, nicht vollständig ausgeführte Transaktion blockiert zu werden. Transaktionen, die Daten ändern, blockieren keine Transaktionen, die Daten lesen; und Transaktionen, die Daten lesen, blockieren keine Transaktionen, die Daten schreiben. Bei der READ COMMITTED-Standardisolationsstufe in SQL Server wäre dies i. d. R. der Fall. Dieses nicht blockierende Verhalten verringert die Wahrscheinlichkeit für Deadlocks bei komplexen Transaktionen beträchtlich.  
  
 Bei der Snapshot-Isolation wird ein Modell der vollständigen Parallelität verwendet. Wenn eine Snapshot-Transaktion versucht, Änderungen an Daten zu speichern, die seit dem Beginn der Transaktion geändert wurden, wird die Transaktion zurückgesetzt und ein Fehler ausgelöst. Dies kann durch das Verwenden von UPDLOCK-Hinweisen für SELECT-Anweisungen verhindert werden, die auf zu ändernde Daten zugreifen. Weitere Informationen finden Sie in der Onlinedokumentation zu SQL Server unter "Locking Hints".  
  
 Die Snapshot-Isolation muss durch das Festlegen der ALLOW_SNAPSHOT_ISOLATION ON-Datenbankoption aktiviert werden, bevor sie in Transaktionen verwendet wird. Dies aktiviert den Mechanismus zum Speichern von Zeilenversionen in der temporären Datenbank (**Tempdb**). Die Snapshot-Isolation muss in jeder Datenbank, die diese verwendet, mit der ALTER DATABASE-Transact-SQL-Anweisung aktiviert werden. In diesem Punkt unterscheidet sich die Snapshot-Isolation von den herkömmlichen Isolationsstufen READ COMMITTED, REPEATABLE READ, SERIALIZABLE und READ UNCOMMITTED, für die keine Konfiguration erforderlich ist. Die folgenden Anweisungen aktivieren die Snapshot-Isolation und ersetzen das READ COMMITTED-Standardverhalten durch SNAPSHOT:  
  
```  
ALTER DATABASE MyDatabase  
SET ALLOW_SNAPSHOT_ISOLATION ON  
  
ALTER DATABASE MyDatabase  
SET READ_COMMITTED_SNAPSHOT ON  
```  
  
 Das Festlegen der READ_COMMITTED_SNAPSHOT ON-Option ermöglicht Zugriff auf versionierte Zeilen mit der READ COMMITTED-Isolationsstufe. Wenn die READ_COMMITTED_SNAPSHOT-Option auf OFF festgelegt ist, müssen Sie die Snapshot-Isolationsstufe für jede Sitzung explizit festlegen, um auf versionierte Zeilen zuzugreifen.  
  
## <a name="managing-concurrency-with-isolation-levels"></a>Verwalten von Parallelität mit Isolationsstufen  
 Die Isolationsstufe, mit der eine Transact-SQL-Anweisung ausgeführt wird, bestimmt das entsprechende Verhalten bei der Sperr- und Zeilenversionserstellung. Eine Isolationsstufe gilt für die gesamte Verbindung, und sobald sie mit der SET TRANSACTION ISOLATION LEVEL-Anweisung für eine Verbindung festgelegt wurde, bleibt sie aktiv, bis die Verbindung geschlossen oder eine andere Isolationsstufe festgelegt wird. Wenn eine Verbindung geschlossen und an den Pool zurückgegeben wird, wird die Isolationsstufe aus der letzten SET TRANSACTION ISOLATION LEVEL-Anweisung beibehalten. Nachfolgende Verbindungen, die eine an den Pool zurückgegebene Verbindung erneut verwenden, verwenden die Isolationsstufe, die zu dem Zeitpunkt gültig war, als die Verbindung an den Pool zurückgegeben wurde.  
  
 Einzelne innerhalb einer Verbindung durchgeführte Abfragen können Sperrhinweise enthalten, die die Isolation für eine einzelne Anweisung oder Transaktion ändern, aber die Isolationsstufe der Verbindung nicht beeinflussen. Isolationsstufen oder Sperrhinweise, die in gespeicherten Prozeduren oder Funktionen festgelegt sind, ändern die Isolationsstufe der aufrufenden Verbindung nicht. Sie sind nur für die Dauer der gespeicherten Prozedur oder des Funktionsaufrufs aktiv.  
  
 In frühen Versionen von SQL Server wurden vier Isolationsstufen unterstützt, die im SQL-92-Standard definiert wurden:  
  
-   READ UNCOMMITTED ist die am wenigsten restriktive Isolationsstufe, da sie von anderen Transaktionen platzierte Sperren ignoriert. Mit READ UNCOMMITTED ausgeführte Transaktionen können geänderte Datenwerte lesen, die noch nicht von anderen Transaktionen gespeichert wurden; diese werden "unsaubere" Lesevorgänge genannt.  
  
-   READ COMMITTED ist die Standardisolationsstufe für SQL Server. Er verhindert "unsaubere" Lesevorgänge, indem festgelegt wird, dass Anweisungen keine Datenwerte lesen können, die geändert, aber noch nicht von anderen Transaktionen gespeichert wurden. Andere Transaktionen können immer noch Daten zwischen Ausführungen einzelner Anweisungen innerhalb der aktuellen Transaktion ändern, einfügen oder löschen, was zu nicht wiederholbaren Lesevorgängen oder "Phantomdaten" führt.  
  
-   REPEATABLE READ ist eine restriktivere Isolationsstufe als READ COMMITTED. Er umfasst READ COMMITTED und gibt zusätzlich an, dass keine andere Transaktion Daten ändern oder löschen kann, die von der aktuellen Transaktion gelesen wurden, bis die aktuelle Transaktion einen Commit durchführt. Die Parallelität ist geringer als bei READ COMMITTED, da gemeinsam verwendete Sperren für gelesene Daten für die Dauer der Transaktion beibehalten und nicht am Ende jeder Anweisung zurückgegeben werden.  
  
-   SERIALIZABLE ist die restriktivste Isolationsstufe, da sie bis zum Abschluss der Transaktion vollständige Schlüsselbereiche sperrt und die Sperren beibehält. Er umfasst REPEATABLE READ und fügt die Einschränkung hinzu, dass andere Transaktionen bis zum Abschluss der Transaktion keine neuen Zeilen in Bereiche einfügen können, die von der Transaktion gelesen wurden.  
  
 Weitere Informationen finden Sie in der Onlinedokumentation zu SQL Server unter "Isolation Levels".  
  
### <a name="snapshot-isolation-level-extensions"></a>Snapshot-Isolationsstufenerweiterungen  
 In SQL Server wurden mit der SNAPSHOT-Isolationsstufe und einer zusätzlichen READ COMMITTED-Implementierung Erweiterungen zu den SQL-92-Isolationsstufen eingeführt. Die READ_COMMITTED_SNAPSHOT-Isolationsstufe kann READ COMMITTED für alle Transaktionen auf transparente Weise ersetzen.  
  
-   SNAPSHOT-Isolation gibt an, dass innerhalb einer Transaktion gelesene Daten niemals Änderungen widerspiegeln, die von anderen gleichzeitigen Transaktionen durchgeführt wurden. Die Transaktion verwendet die Datenzeilenversionen, die zu Beginn der Transaktion vorhanden sind. Beim Lesen der Daten werden keine Sperren erstellt, deshalb blockieren SNAPSHOT-Transaktionen das Schreiben von Daten durch andere Transaktionen nicht. Transaktionen, die Daten schreiben, blockieren das Lesen von Daten durch andere Transaktionen nicht. Um die Snapshot-Isolation verwenden zu können, müssen Sie die ALLOW_SNAPSHOT_ISOLATION-Datenbankoption aktivieren.  
  
-   Die READ_COMMITTED_SNAPSHOT-Datenbankoption bestimmt das Verhalten der READ COMMITTED-Standardisolationsstufe, wenn Snapshot-Isolation in einer Datenbank aktiviert ist. Wenn Sie READ_COMMITTED_SNAPSHOT ON nicht explizit angeben, wird READ COMMITTED für alle impliziten Transaktionen angewendet. Dies führt zum gleichen Verhalten wie beim Festlegen von READ_COMMITTED_SNAPSHOT auf OFF (Standardeinstellung). Wenn READ_COMMITTED_SNAPSHOT auf OFF festgelegt ist, verwendet die Datenbank-Engine gemeinsame Sperren, um die Standardisolationsstufe zu erzwingen. Wenn Sie die READ_COMMITTED_SNAPSHOT-Datenbankoption auf ON festlegen, verwendet die Datenbank-Engine Zeilenversionserstellung und die Snapshot-Isolation als Standard, anstatt Sperren zum Schutz der Daten zu verwenden.  
  
## <a name="how-snapshot-isolation-and-row-versioning-work"></a>Funktionsweise der Snapshot-Isolation und der Zeilenversionserstellung  
 Wenn die SNAPSHOT-Isolationsstufe, jedes Mal aktiviert ist eine Zeile aktualisiert wird, die SQL Server-Datenbank-Engine speichert eine Kopie der Ursprungszeile in **Tempdb**, und der Zeile eine Transaktionsfolgenummer hinzugefügt. Nachfolgend ist die Reihenfolge der Ereignisse angegeben:  
  
-   Eine neue Transaktion wird initiiert, und ihr wird eine Transaktionsfolgenummer zugewiesen.  
  
-   Das Datenbankmodul liest eine Zeile innerhalb der Transaktion und ruft die Zeilenversion aus **Tempdb** , deren Nummer ist, am nächsten liegt und kleiner ist als die Sequenznummer der Transaktion.  
  
-   Die Datenbank-Engine prüft, ob die Transaktionsfolgenummer in der Liste von Transaktionsfolgenummern der nicht übernommenen Transaktionen vorhanden ist, die beim Start der Snapshot-Transaktion aktiv waren.  
  
-   Die Transaktion liest die Version der Zeile aus **Tempdb** , ab dem Beginn der Transaktion aktuell war. Nach dem Start der Transaktion kann diese keine neu eingefügten Zeilen erfassen, da diese Folgenummernwerte höher sind als der Wert der Transaktionsfolgenummer.  
  
-   Die aktuelle Transaktion sehen die Zeilen, die gelöscht wurden, nach dem Beginn der Transaktion eine Zeilenversion in werden, da **Tempdb** mit einem niedrigeren Sequence-Number-Wert.  
  
 Das Ergebnis der Snapshot-Isolation besteht darin, dass die Transaktion alle Daten so erfasst, wie sie zum Transaktionsstart vorhanden waren, ohne für die zugrunde liegenden Tabellen Sperren umzusetzen oder zu platzieren. Dies kann in Situationen mit Konflikten zu einer Leistungssteigerung führen.  
  
 Eine Snapshot-Transaktion verwendet immer vollständige Parallelitätssteuerung, wobei alle Sperren zurückgehalten werden, die das Aktualisieren von Zeilen durch andere Transaktionen verhindern. Wenn eine Snapshot-Transaktion versucht, ein Update für eine Zeile zu übernehmen, die nach dem Beginn der Transaktion geändert wurde, wird die Transaktion zurückgenommen und ein Fehler ausgelöst.  
  
## <a name="working-with-snapshot-isolation-in-adonet"></a>Verwenden der Snapshot-Isolation in ADO.NET  
 Die Snapshot-Isolation wird in ADO.NET durch die <xref:System.Data.SqlClient.SqlTransaction>-Klasse unterstützt. Wenn eine Datenbank für die Snapshot-Isolation aktiviert wurde, aber nicht für READ_COMMITTED_SNAPSHOT ON konfiguriert ist, müssen Sie Initiieren einer <xref:System.Data.SqlClient.SqlTransaction> mithilfe der **IsolationLevel.Snapshot** Enumerationswert beim Aufrufen der <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> -Methode. Für dieses Codefragment wird angenommen, dass es sich bei der Verbindung um ein offenes <xref:System.Data.SqlClient.SqlConnection>-Objekt handelt.  
  
```vb  
Dim sqlTran As SqlTransaction = _  
  connection.BeginTransaction(IsolationLevel.Snapshot)  
```  
  
```csharp  
SqlTransaction sqlTran =   
  connection.BeginTransaction(IsolationLevel.Snapshot);  
```  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie sich die verschiedenen Isolationsstufen beim Zugriff auf gesperrte Daten verhalten. Dieses Beispiel ist nicht zur Verwendung in Produktionscode bestimmt.  
  
 Der Code eine Verbindung herstellt, um die **AdventureWorks** Beispieldatenbank in SQL Server und erstellt eine Tabelle namens **TestSnapshot** und fügt eine Zeile mit Daten. Der Code verwendet die ALTER DATABASE Transact-SQL-Anweisung zum Aktivieren der Snapshot-Isolation für die Datenbank, legt aber nicht die READ_COMMITTED_SNAPSHOT-Option fest, wodurch das READ COMMITTED-Isolationsstufenverhalten bestehen bleibt. Der Code führt dann die folgenden Aktionen aus:  
  
-   Er startet sqlTransaction1, die die SERIALIZABLE-Isolationsstufe verwendet, um eine Updatetransaktion zu starten. sqlTransaction1 wird allerdings nicht fertig gestellt. Dadurch wird die Tabelle gesperrt.  
  
-   Er öffnet eine zweite Verbindung und initiiert eine zweite Transaktion mit der SNAPSHOT-Isolationsstufe zum Lesen der Daten in die **TestSnapshot** Tabelle. Da die Snapshot-Isolation aktiviert ist, kann diese Transaktion die Daten lesen, die vor dem Start von sqlTransaction1 vorhanden waren.  
  
-   Der Code öffnet eine dritte Verbindung und initiiert eine Transaktion mit der READ COMMITED-Isolationsstufe, um die Daten in der Tabelle zu lesen. In diesem Fall kann der Code die Daten nicht lesen, weil er nicht über die Sperren hinweg lesen kann, die in der ersten Transaktion für die Tabelle platziert wurden, und löst eine Zeitüberschreitung aus. Das gleiche Ergebnis tritt auch bei den Isolationsstufen REPEATABLE READ und SERIALIZABLE auf, weil diese Isolationsstufen ebenfalls nicht über die in der ersten Transaktion platzierten Sperren hinweg lesen können.  
  
-   Der Code öffnet eine vierte Verbindung und initiiert mit der READ UNCOMMITTED-Isolationsstufe eine Transaktion, die einen "unsauberen" Lesevorgang für den nicht übernommenen Wert in sqlTransaction1 durchführt. Dieser Wert ist möglicherweise tatsächlich nie in der Datenbank vorhanden, wenn die erste Transaktion nicht übernommen wird.  
  
-   Er führt einen Rollback für die erste Transaktion und Bereinigung durch, indem die **TestSnapshot** snapshot-Isolation für Tabelle und zum Ausschalten der **AdventureWorks** Datenbank.  
  
> [!NOTE]
>  In den folgenden Beispielen wird dieselbe Verbindungszeichenfolge verwendet, wobei aber das Verbindungspooling deaktiviert ist. Wenn sich eine Verbindung in einem Pool befindet, führt die Rücksetzung ihrer Isolationsstufe nicht automatisch auch zur Rücksetzung der Isolationsstufe auf dem Server. Nachfolgende Verbindungen, die dieselbe innere Verbindung aus dem Pool verwenden, beginnen daher mit der Isolationsstufe, die für die Verbindung im Pool festgelegt ist. Alternativ zum Deaktivieren des Verbindungspoolings können Sie auch die Isolationsstufe explizit für jede Verbindung festlegen.  
  
 [!code-csharp[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/VB/source.vb#1)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Verhalten der Snapshot-Isolation beim Ändern von Daten gezeigt. Der Code führt die folgenden Aktionen aus:  
  
-   Stellt eine Verbindung her, um die **AdventureWorks** Beispiel her und aktiviert die SNAPSHOT-Isolation.  
  
-   Erstellt eine Tabelle namens **TestSnapshotUpdate** und fügt drei Zeilen mit Beispieldaten.  
  
-   Startet sqlTransaction1 mit einer SNAPSHOT-Isolation, stellt diese aber nicht fertig. In der Transaktion werden drei Zeilen mit Daten ausgewählt.  
  
-   Erstellt eine zweite **SqlConnection** zu **AdventureWorks** und erstellt eine zweite Transaktion mit der READ COMMITTED-Isolationsstufe, die einen Wert in einer der in sqlTransaction1 ausgewählten Zeilen aktualisiert.  
  
-   Führt einen Commit für sqlTransaction2 durch.  
  
-   Kehrt zu sqlTransaction1 zurück und versucht, dieselbe Zeile zu aktualisieren, für die sqlTransaction1 bereits einen Commit durchgeführt hat. Der Fehler 3960 wird ausgelöst, und sqlTransaction1 wird automatisch zurückgenommen. Die **SqlException.Number** und **SqlException.Message** werden im Konsolenfenster angezeigt.  
  
-   Führt Bereinigungscode deaktivieren Sie die Snapshot-Isolation in **AdventureWorks** und löschen Sie die **TestSnapshotUpdate** Tabelle.  
  
 [!code-csharp[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/VB/source.vb#1)]  
  
### <a name="using-lock-hints-with-snapshot-isolation"></a>Verwenden von Sperrhinweisen mit der Snapshot-Isolation  
 Im vorigen Beispiel wählt die erste Transaktion Daten aus, und eine zweite Transaktion aktualisiert die Daten, bevor die erste Transaktion beendet werden kann, wodurch ein Updatekonflikt entsteht, wenn die erste Transaktion versucht, dieselbe Zeile zu aktualisieren. Sie können die Gefahr von Updatekonflikten in Snapshot-Transaktionen mit langen Laufzeiten reduzieren, indem Sie zu Beginn der Transaktionen Sperrhinweise bereitstellen. In der folgenden SELECT-Anweisung wird der UPDLOCK-Hinweis zum Sperren der ausgewählten Zeilen verwendet:  
  
```  
SELECT * FROM TestSnapshotUpdate WITH (UPDLOCK)   
  WHERE PriKey BETWEEN 1 AND 3  
```  
  
 Mit dem UPDLOCK-Sperrhinweis werden alle Zeilen blockiert, die versuchen, die Zeilen vor dem Fertigstellen der ersten Transaktion zu aktualisieren. Dadurch wird gewährleistet, dass die ausgewählten Zeilen fehlerfrei sind, wenn sie später in der Transaktion aktualisiert werden. Weitere Informationen finden Sie in der Onlinedokumentation zu SQL Server unter "Locking Hints".  
  
 Wenn eine Anwendung viele Konflikte aufweist, stellt die Snapshot-Isolation möglicherweise nicht die optimale Vorgehensweise dar. Hinweise sollten nur verwendet werden, wenn sie wirklich erforderlich sind. Eine Anwendung sollte nicht so erstellt werden, dass ihre Ausführung stets von Sperrhinweisen abhängt.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
