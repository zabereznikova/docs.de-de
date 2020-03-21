---
title: Momentaufnahmenisolation in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43ae5dd3-50f5-43a8-8d01-e37a61664176
ms.openlocfilehash: 8313ffc8eef70c1e5efc24b09a160edb7cec1595
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174263"
---
# <a name="snapshot-isolation-in-sql-server"></a>Momentaufnahmenisolation in SQL Server
Die Momentaufnahmenisolation verbessert die Parallelität für OLTP-Anwendungen.  
  
## <a name="understanding-snapshot-isolation-and-row-versioning"></a>Informationen zur Snapshot-Isolation und Zeilenversionserstellung  
 Sobald die Snapshot-Isolation aktiviert ist, müssen aktualisierte Zeilenversionen für jede Transaktion beibehalten werden.  Vor SQL Server 2019 wurden diese Versionen in **tempdb**gespeichert. SQL Server 2019 führt eine neue Funktion ein, Accelerated Database Recovery (ADR), die einen eigenen Satz von Zeilenversionen erfordert.  Wenn Also ab SQL Server 2019 ADR nicht aktiviert ist, werden Zeilenversionen wie immer in **tempdb** beibehalten.  Wenn ADR aktiviert ist, werden alle Zeilenversionen, die sich beide auf die Snapshot-Isolation und ADR beziehen, im Persistent Version Store (PVS) von ADR gespeichert, der sich in der Benutzerdatenbank in einer Dateigruppe befindet, die der Benutzer angibt. Eine eindeutige Transaktionssequenznummer identifiziert jede Transaktion, wobei diese eindeutigen Nummern für jede Zeilenversion aufgezeichnet werden. Die Transaktion arbeitet mit den neuesten Zeilenversionen, die eine Sequenznummer vor der Sequenznummer der Transaktion haben. Neuere Zeilenversionen, die nach Beginn der Transaktion erstellt wurden, werden von der Transaktion ignoriert.  
  
 Der Begriff „Momentaufnahme“ spiegelt die Tatsache wider, dass alle Abfragen in der Transaktion die gleiche Version bzw. Momentaufnahme der Datenbank sehen, und zwar basierend auf dem Zustand der Datenbank zum Zeitpunkt des Transaktionsbeginns. In einer Snapshot-Transaktion werden für die zugrunde liegenden Datenzeilen oder Datenseiten keine Sperren bezogen, wodurch andere Transaktionen ausgeführt werden können, ohne durch eine vorherige, nicht vollständig ausgeführte Transaktion blockiert zu werden. Transaktionen, die Daten ändern, blockieren keine Transaktionen, die Daten lesen. Transaktionen, die Daten lesen, blockieren keine Transaktionen, die Daten schreiben. Dies ist bei der Standardisolationsstufe READ COMMITTED in SQL Server normalerweise der Fall. Dieses nicht blockierende Verhalten verringert auch beträchtlich die Wahrscheinlichkeit für Deadlocks bei komplexen Transaktionen.  
  
 Für die Momentaufnahmenisolation wird ein optimistisches Parallelitätsmodell verwendet. Wenn eine Momentaufnahmentransaktion versucht, Änderungen an Daten zu committen, die sich seit Beginn der Transaktion geändert haben, wird die Transaktion rückgängig gemacht und ein Fehler ausgelöst. Sie können dies vermeiden, indem Sie UPDLOCK-Hinweise für SELECT-Anweisungen verwenden, die auf zu ändernde Daten zugreifen. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation unter „Sperrhinweise“.  
  
 Die Momentaufnahmenisolation muss durch Festlegen der Datenbankoption ALLOW_SNAPSHOT_ISOLATION ON aktiviert werden, bevor sie in Transaktionen verwendet wird. Dadurch wird der Mechanismus zum Speichern von Zeilenversionen in der temporären Datenbank (**tempdb**) aktiviert. Sie müssen die Momentaufnahmenisolation in jeder Datenbank aktivieren, die sie mit der Transact-SQL-Anweisung ALTER DATABASE verwendet. In dieser Hinsicht unterscheidet sich die Momentaufnahmenisolation von den herkömmlichen Isolationsstufen READ COMMITTED, REPEATABLE READ, SERIALIZABLE und READ UNCOMMITTED, die keine Konfiguration erfordern. Die folgenden Anweisungen aktivieren die Momentaufnahmenisolation und ersetzen das Standardverhalten von READ COMMITTED durch SNAPSHOT:  
  
```sql  
ALTER DATABASE MyDatabase  
SET ALLOW_SNAPSHOT_ISOLATION ON  
  
ALTER DATABASE MyDatabase  
SET READ_COMMITTED_SNAPSHOT ON  
```  
  
 Das Festlegen der Option READ_COMMITTED_SNAPSHOT auf ON ermöglicht den Zugriff auf Zeilen mit Versionsangabe unter der Standardisolationsstufe READ_COMMITTED. Wenn die Option READ_COMMITTED_SNAPSHOT auf OFF festgelegt ist, müssen Sie die Isolationsstufe für Momentaufnahmen für jede Sitzung explizit festlegen, um auf Zeilen mit Versionsangabe zugreifen zu können.  
  
## <a name="managing-concurrency-with-isolation-levels"></a>Verwalten von Parallelität mit Isolationsstufen  
 Die Isolationsstufe, auf der eine Transact-SQL-Anweisung ausgeführt wird, bestimmt ihr Sperr- und Zeilenversionsverwaltungs-Verhalten. Eine Isolationsstufe gilt verbindungsweit. Sobald sie für eine Verbindung mit der Anweisung SET TRANSACTION ISOLATION LEVEL festgelegt wurde, bleibt sie in Kraft, bis die Verbindung geschlossen oder eine andere Isolationsstufe festgelegt wird. Wenn eine Verbindung geschlossen und an den Pool zurückgegeben wird, wird die Isolationsstufe der letzten SET TRANSACTION ISOLATION LEVEL-Anweisung beibehalten. Nachfolgende Verbindungen, die eine Verbindung im Pool wiederverwenden, arbeiten mit der Isolationsstufe, die zum Zeitpunkt des Hinzufügens zum Pool in Kraft war.  
  
 Einzelne innerhalb einer Verbindung gestellte Abfragen können Sperrhinweise enthalten, die die Isolation für eine einzelne Anweisung oder Transaktion ändern, aber die Isolationsstufe der Verbindung nicht beeinflussen. In gespeicherten Prozeduren oder Funktionen festgelegte Isolationsstufen oder Sperrhinweise ändern die Isolationsstufe der Verbindung, die sie aufruft, nicht und sind nur für die Dauer des Aufrufs der gespeicherten Prozedur oder Funktion wirksam.  
  
 In frühen Versionen von SQL Server wurden vier im Standard SQL-92 definierte Isolationsstufen unterstützt:  
  
- READ UNCOMMITTED ist die am wenigsten restriktive Isolationsstufe, da sie Sperren ignoriert, die von anderen Transaktionen aktiviert wurden. Transaktionen, die unter READ UNCOMMITTED ausgeführt werden, können geänderte Datenwerte lesen, die noch nicht von anderen Transaktionen committet wurden. Diese werden als „Dirty Reads“ bezeichnet.  
  
- Die Standardisolationsstufe für SQL Server ist READ COMMITTED. Sie verhindert Dirty Reads, indem sie festlegt, dass Anweisungen keine Datenwerte lesen können, die zwar geändert, aber noch nicht von anderen Transaktionen committet wurden. Andere Transaktionen können nach wie vor Daten zwischen der Ausführung einzelner Anweisungen innerhalb der aktuellen Transaktion ändern, einfügen oder löschen, was zu nicht wiederholbaren Lesevorgängen oder „Phantomdaten“ führt.  
  
- REPEATABLE READ ist eine restriktivere Isolationsstufe als READ COMMITTED. Sie umfasst READ COMMITTED und legt zusätzlich fest, dass keine anderen Transaktionen Daten, die von der aktuellen Transaktion gelesen wurden, ändern oder löschen können, bis die aktuelle Transaktion committet wurde. Die Parallelität ist geringer als bei READ COMMITTED, da gemeinsame Sperren für gelesene Daten für die Dauer der Transaktion bestehen bleiben, anstatt am Ende jeder Anweisung freigegeben zu werden.  
  
- SERIALIZABLE ist die restriktivste Isolationsstufe, da gesamte Schlüsselbereiche gesperrt werden, und die Sperren bis zum Abschluss der Transaktion aufrechterhalten werden. Sie umfasst REPEATABLE READ und fügt die Einschränkung hinzu, dass andere Transaktionen keine neuen Zeilen in Bereiche einfügen können, die von der Transaktion gelesen wurden, bis die Transaktion abgeschlossen ist.  
  
 Weitere Informationen finden Sie im [Handbuch zu Transaktionssperren und Zeilenversionsverwaltung](/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide).  
  
### <a name="snapshot-isolation-level-extensions"></a>Snapshot-Isolationsstufenerweiterungen  
 SQL Server hat Erweiterungen für die SQL-92-Isolationsgrade eingeführt, zu denen der SNAPSHOT-Isolationsgrad und eine zusätzliche Implementierung von READ COMMITTED gehört. Der READ_COMMITTED_SNAPSHOT-Isolationsgrad kann auf transparente Weise READ COMMITTED für alle Transaktionen ersetzen.  
  
- Die SNAPSHOT-Isolation legt fest, dass Daten, die innerhalb einer Transaktion gelesen werden, niemals Änderungen widerspiegeln, die durch andere gleichzeitige Transaktionen vorgenommen wurden. Die Transaktion verwendet die Datenzeilenversionen, die zu Beginn der Transaktion vorhanden sind. Beim Lesen werden keine Sperren für die Daten aktiviert, sodass SNAPSHOT-Transaktionen andere Transaktionen nicht am Schreiben von Daten hindern. Transaktionen, die Daten schreiben, halten SNAPSHOT-Transaktionen nicht vom Lesen von Daten ab. Sie müssen die Momentaufnahmenisolation durch Festlegen der Datenbankoption ALLOW_SNAPSHOT_ISOLATION aktivieren, um sie verwenden zu können.  
  
- Die Datenbankoption READ_COMMITTED_SNAPSHOT bestimmt das Verhalten der Standardisolationsstufe READ COMMITTED, wenn die Momentaufnahmenisolation in einer Datenbank aktiviert ist. Wenn Sie ON für READ_COMMITTED_SNAPSHOT nicht explizit angeben, gilt READ COMMITTED für alle impliziten Transaktionen. Dies führt zum selben Verhalten wie das Festlegen von READ_COMMITTED_SNAPSHOT auf OFF (Standard). Wenn OFF für READ_COMMITTED_SNAPSHOT aktiviert ist, verwendet die Datenbank-Engine gemeinsame Sperren, um die Standardisolationsstufe zu erzwingen. Wenn Sie die Datenbankoption READ_COMMITTED_SNAPSHOT auf ON festlegen, verwendet die Datenbank-Engine standardmäßig die Zeilenversionsverwaltung und Momentaufnahmenisolation, anstatt Sperren zum Schutz der Daten einzusetzen.  
  
## <a name="how-snapshot-isolation-and-row-versioning-work"></a>Funktionsweise der Snapshot-Isolation und der Zeilenversionserstellung  
 Wenn die SNAPSHOT-Isolationsstufe aktiviert ist, speichert die SQL Server-Datenbank-Engine bei jedem Aktualisieren einer Zeile eine Kopie der Ursprungszeile in **tempdb** und fügt der Zeile eine Transaktionsfolgenummer hinzu. Es folgt die Abfolge der eintretenden Ereignisse:  
  
- Eine neue Transaktion wird eingeleitet, der eine Transaktionssequenznummer zugewiesen wird.  
  
- Die Datenbank-Engine liest eine Zeile innerhalb der Transaktion und ruft die Zeilenversion von **tempdb** ab, deren Nummer kleiner ist als die Transaktionsfolgenummer und gleichzeitig am nächsten bei dieser liegt.  
  
- Die Datenbank-Engine prüft, ob die Transaktionssequenznummer nicht in der Liste der Transaktionssequenznummern der nicht committeten Transaktionen enthalten ist, die beim Start der Momentaufnahmentransaktion aktiv waren.  
  
- Die Transaktion liest in **tempdb** die Version der Zeile, die beim Start der Transaktion aktuell war. Es werden keine neuen Zeilen eingefügt, nachdem die Transaktion gestartet wurde, da diese Sequenznummernwerte höher als der Wert der Transaktionssequenznummer sind.  
  
- Die aktuelle Transaktion erfasst Zeilen, die nach dem Start der Transaktion gelöscht wurden, weil in **tempdb** eine Zeilenversion mit niedrigerem Folgenummernwert vorhanden ist.  
  
 Der Nutzeffekt der Momentaufnahmenisolation besteht darin, dass die Transaktion alle Daten so sieht, wie sie zu Beginn der Transaktion vorhanden waren, ohne die zugrunde liegenden Tabellen zu berücksichtigen oder zu sperren. Dies kann in Konfliktsituationen zu Leistungsverbesserungen führen.  
  
 Eine Momentaufnahmentransaktion verwendet immer eine optimistische Parallelitätssteuerung, wobei alle Sperren zurückgehalten werden, die andere Transaktionen an der Aktualisierung von Zeilen hindern würden. Wenn eine Momentaufnahmentransaktion versucht, eine Aktualisierung einer Zeile zu committen, die nach Beginn der Transaktion geändert wurde, wird die Transaktion rückgängig gemacht und ein Fehler ausgelöst.  
  
## <a name="working-with-snapshot-isolation-in-adonet"></a>Verwenden der Snapshot-Isolation in ADO.NET  
 Die Momentaufnahmenisolation wird in ADO.NET von der <xref:System.Data.SqlClient.SqlTransaction>-Klasse unterstützt. Wenn eine Datenbank für die Snapshot-Isolation aktiviert, aber nicht für READ_COMMITTED_SNAPSHOT ON konfiguriert wurde, müssen Sie eine <xref:System.Data.SqlClient.SqlTransaction> mit dem **IsolationLevel.Snapshot**-Enumerationswert initiieren, wenn Sie die <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A>-Methode aufrufen. Dieses Codefragment geht davon aus, dass die Verbindung ein geöffnetes <xref:System.Data.SqlClient.SqlConnection>-Objekt ist.  
  
```vb  
Dim sqlTran As SqlTransaction = _  
  connection.BeginTransaction(IsolationLevel.Snapshot)  
```  
  
```csharp  
SqlTransaction sqlTran =
  connection.BeginTransaction(IsolationLevel.Snapshot);  
```  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Verhalten der verschiedenen Isolationsstufen beim Versuch, auf gesperrte Daten zuzugreifen. Es ist nicht für die Verwendung im Produktionscode vorgesehen.  
  
 Der Code stellt eine Verbindung mit der **AdventureWorks**-Beispieldatenbank in SQL Server her, erstellt die Tabelle **TestSnapshot** und fügt eine Datenzeile ein. Der Code verwendet die Transact-SQL-Anweisung ALTER DATABASE, um die Momentaufnahmenisolation für die Datenbank zu aktivieren. Die Option READ_COMMITTED_SNAPSHOT wird jedoch nicht festgelegt, sodass das Standardverhalten der Isolationsstufe READ_COMMITTED weiterhin gilt. Der Code führt dann die folgenden Aktionen aus:  
  
- Er beginnt sqlTransaction1, ohne sie jedoch abzuschließen, die die Isolationsstufe SERIALIZABLE verwendet, um eine Aktualisierungstransaktion zu starten. Dies hat Auswirkungen auf das Sperren der Tabelle.  
  
- Der Code öffnet eine zweite Verbindung und initiiert eine zweite Transaktion mit der SNAPSHOT-Isolationsstufe zum Lesen der Daten in der **TestSnapshot**-Tabelle. Da die Momentaufnahmenisolation aktiviert ist, kann diese Transaktion die Daten lesen, die vor dem Start von sqlTransaction1 vorhanden waren.  
  
- Der Code öffnet eine dritte Verbindung und leitet eine Transaktion mit der Isolationsstufe READ COMMITTED ein, um zu versuchen, die Daten in der Tabelle zu lesen. In diesem Fall kann der Code die Daten nicht lesen, da er nicht über die Sperren lesen kann, die in der ersten Transaktion für die Tabelle platziert wurden, und eine Zeitauferung. Das gleiche Ergebnis würde auftreten, wenn die Isolationsstufen REPEATABLE READ und SERIALIZABLE verwendet würden, da diese Isolationsstufen auch nicht über die in der ersten Transaktion platzierten Sperren lesen können.  
  
- Der Code öffnet eine vierte Verbindung und leitet eine Transaktion mit der Isolationsstufe READ UNCOMMITTED ein, die einen Dirty Read des nicht committeten Werts in sqlTransaction1 durchführt. Dieser Wert ist möglicherweise nie wirklich in der Datenbank vorhanden, wenn die erste Transaktion nicht committet wird.  
  
- Der Code nimmt die erste Transaktion zurück und führt eine Bereinigung durch, indem er die **TestSnapshot**-Tabelle löscht und die Snapshot-Isolation für die **AdventureWorks**-Datenbank deaktiviert.  
  
> [!NOTE]
> Die folgenden Beispiele verwenden dieselbe Verbindungszeichenfolge bei deaktiviertem Verbindungspooling. Wenn eine Verbindung in einem Pool vorhanden ist, wird durch das Zurücksetzen der Isolationsstufe die Isolationsstufe auf dem Server nicht zurückgesetzt. Infolgedessen beginnen nachfolgende Verbindungen, die dieselbe innere Poolverbindung verwenden, mit der Isolationsstufe, die auf die der Poolverbindung festgelegt ist. Eine Alternative zum Deaktivieren des Verbindungspoolings besteht darin, die Isolationsstufe für jede Verbindung explizit festzulegen.  
  
 [!code-csharp[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/VB/source.vb#1)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Verhalten der Momentaufnahmenisolation, wenn Daten geändert werden. Der Code führt die folgenden Aktionen aus:  
  
- Herstellen einer Verbindung mit der **AdventureWorks**-Beispieldatenbank und Aktivieren der SNAPSHOT-Isolation.  
  
- Erstellen der Tabelle **TestSnapshotUpdate** und Einfügen von drei Zeilen mit Beispieldaten.  
  
- sqlTransaction1 wird mit SNAPSHOT-Isolation gestartet, aber nicht abgeschlossen. In der Transaktion sind drei Datenzeilen ausgewählt.  
  
- Erstellt eine zweite **SqlConnection** mit **AdventureWorks** und erstellt eine zweite Transaktion mit der READ COMMITTED-Isolationsstufe, die einen Wert in einer der in sqlTransaction1 ausgewählten Zeilen aktualisiert.  
  
- Committet sqlTransaction2.  
  
- Kehrt zu sqlTransaction1 zurück und versucht, dieselbe Zeile zu aktualisieren, für die sqlTransaction1 bereits committet wurde. Fehler 3960 wird ausgelöst, und für sqlTransaction1 wird automatisch ein Rollback ausgeführt. Im Konsolenfenster werden die **SqlException.Number** und die **SqlException.Message** angezeigt.  
  
- Führt Bereinigungscode aus, um die Snapshot-Isolation in **AdventureWorks** zu deaktivieren und die **TestSnapshotUpdate**-Tabelle zu löschen.  
  
 [!code-csharp[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/VB/source.vb#1)]  
  
### <a name="using-lock-hints-with-snapshot-isolation"></a>Verwenden von Sperrhinweisen mit der Snapshot-Isolation  
 Im vorherigen Beispiel wählt die erste Transaktion Daten aus. Eine zweite Transaktion aktualisiert die Daten, bevor die erste Transaktion abgeschlossen werden kann. Dadurch entsteht ein Aktualisierungskonflikt, wenn die erste Transaktion versucht, dieselbe Zeile zu aktualisieren. Sie können die Wahrscheinlichkeit von Aktualisierungskonflikten bei lang laufenden Momentaufnahmentransaktionen verringern, indem Sie zu Beginn der Transaktion Sperrhinweise angeben. Die folgende SELECT-Anweisung verwendet den UPDLOCK-Hinweis, um die ausgewählten Zeilen zu sperren:  
  
```sql  
SELECT * FROM TestSnapshotUpdate WITH (UPDLOCK)
  WHERE PriKey BETWEEN 1 AND 3  
```  
  
 Die Verwendung des UPDLOCK-Sperrhinweises blockiert alle Zeilen, die versuchen, die Zeilen zu aktualisieren, bevor die erste Transaktion abgeschlossen ist. Dies garantiert, dass die ausgewählten Zeilen keine Konflikte aufweisen, wenn sie später in der Transaktion aktualisiert werden. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation unter „Sperrhinweise“.  
  
 Wenn Ihre Anwendung viele Konflikte aufweist, ist die Momentaufnahmenisolation möglicherweise nicht die beste Wahl. Hinweise sollten nur verwendet werden, wenn unbedingt nötig. Ihre Anwendung sollte nicht so konzipiert sein, dass ihr Betrieb ständig auf Sperrhinweise angewiesen ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
- [Handbuch zu Transaktionssperren und Zeilenversionsverwaltung](/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide)
