---
title: Häufig gestellte Fragen (FAQs)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634702"
---
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen (FAQs)

In den folgenden Abschnitten werden einige häufige Probleme erläutert, die bei der Implementierung von LINQ auftreten können.

Bei der [Problem](troubleshooting.md)Behandlung werden weitere Probleme behandelt.

## <a name="cannot-connect"></a>Verbindung kann nicht hergestellt werden

F. Es kann keine Verbindung mit meiner Datenbank hergestellt werden.

A. Stellen Sie sicher, dass Ihre Verbindungs Zeichenfolge richtig ist und dass die SQL Server Instanz ausgeführt wird. Beachten Sie auch, dass für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das Named Pipes-Protokoll aktiviert sein muss. Weitere Informationen finden Sie unter [lernen durch](learning-by-walkthroughs.md)Exemplarische Vorgehensweisen.

## <a name="changes-to-database-lost"></a>Änderungen an der Datenbank sind nicht vorhanden

F. Änderungen an den Daten in der Datenbank sind nicht mehr vorhanden, nachdem meine Anwendung erneut ausgeführt wurde.

A. Stellen Sie sicher, dass Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, um Ergebnisse in der Datenbank zu speichern.

## <a name="database-connection-open-how-long"></a>Wie lange kann die Datenbankverbindung geöffnet bleiben?

F. Wie lange bleibt meine Datenbankverbindung geöffnet?

A. Eine Verbindung bleibt normalerweise geöffnet, bis Sie die Abfrageergebnisse verwenden. Wenn Sie erwarten, dass die Verarbeitung sämtlicher Ergebnisse länger dauert und nichts dagegen spricht, die Ergebnisse zwischenzuspeichern, wenden Sie <xref:System.Linq.Enumerable.ToList%2A> auf die Abfrage an. In gängigen Szenarien, in denen jedes Objekt nur einmal verarbeitet wird, ist das Streamingmodell sowohl in `DataReader` als auch in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die bevorzugte Lösung.

Die genauen Details der Verbindungsnutzung hängen von folgenden Faktoren ab:

- Verbindungsstatus, wenn <xref:System.Data.Linq.DataContext> mit einem Verbindungsobjekt erstellt wird.

- Verbindungszeichenfolgen-Einstellungen (z. B. Aktivieren von MARS (Multiple Active Result Sets)). Weitere Informationen finden Sie unter [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).

## <a name="updating-without-querying"></a>Ausführen von Updates ohne Abfrage

F. Können Tabellendaten aktualisiert werden, ohne zuerst eine Datenbankabfrage auszuführen?

A. Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine mengenbasierten Updatebefehle bereitstellt, können Sie mithilfe einer der folgenden Techniken ohne vorherige Abfrage ein Update ausführen:

- Verwenden Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>, um SQL-Code zu senden.

- Erstellen Sie eine neue Instanz des Objekts, und initialisieren Sie alle aktuellen Werte (Felder), die sich auf das Update auswirken. Fügen Sie das Objekt anschließend mithilfe von <xref:System.Data.Linq.DataContext> an <xref:System.Data.Linq.Table%601.Attach%2A> an, und ändern Sie das gewünschte Feld.

## <a name="unexpected-query-results"></a>Unerwartete Abfrageergebnisse

F. Meine Abfrage gibt unerwartete Ergebnisse zurück. Wie kann der Fehler festgestellt werden?

A. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt mehrere Tools zum Überprüfen des generierten SQL-Codes bereit. Eines der wichtigsten Tools ist <xref:System.Data.Linq.DataContext.Log%2A>. Weitere Informationen finden Sie [unter Debuggingunterstützung](debugging-support.md).

## <a name="unexpected-stored-procedure-results"></a>Gespeicherte Prozedur gibt unerwartete Ergebnisse zurück

F. Der Rückgabewert einer gespeicherten Prozedur wird durch `MAX()` berechnet. Wenn Sie die gespeicherte Prozedur auf die O/R-Designer-Oberfläche ziehen, ist der Rückgabewert nicht richtig.

A. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet zwei Möglichkeiten, von der Datenbank generierte Werte mithilfe gespeicherter Prozeduren zurückzugeben:

- Durch Benennen des Ausgabeergebnisses.

- Durch explizites Festlegen eines Ausgabeparameters.

Im Folgenden ein Beispiel für eine fehlerhafte Ausgabe. Da die Ergebnisse von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht zugeordnet werden können, wird immer 0 zurückgegeben:

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der ein Ausgabeparameter verwendet wird:

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der das Ausgabeergebnis benannt wird:

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

Weitere Informationen finden Sie unter [Anpassen von Vorgängen mithilfe von gespeicherten Prozeduren](customizing-operations-by-using-stored-procedures.md).

## <a name="serialization-errors"></a>Serialisierungsfehler

F. Beim Versuch, die Serialisierung auszuführen, erhalte ich den folgenden Fehler: "Type ' System. Data. Linq. ChangeTracker + standardchangetracker '... ist nicht als serialisierbar gekennzeichnet. "

A. Die Codegenerierung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet Unterstützung für die <xref:System.Runtime.Serialization.DataContractSerializer>-Serialisierung. <xref:System.Xml.Serialization.XmlSerializer> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> wird nicht unterstützt. Weitere Informationen finden Sie unter [Serialization (Serialisierung)](serialization.md).

## <a name="multiple-dbml-files"></a>Mehrere DBML-Dateien

F. Bei Verwendung mehrerer DBML-Dateien, die einige Tabellen gemeinsam nutzen, wird ein Compilerfehler ausgegeben.

A. Legen Sie die Eigenschaften für den **Kontext Namespace** und den **Entitäts Namespace** aus dem objektrelationaler Designer auf einen eindeutigen Wert für jede DBML-Datei fest. Durch diese Lösung werden Konflikte zwischen Namen und Namespace vermieden.

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a>Vermeiden, dass von der Datenbank generierte Werte bei Einfüge- oder Updatevorgängen explizit festgelegt werden

F. Bei einer Datenbanktabelle mit einer `DateCreated`-Spalte wird die Spalte standardmäßig auf SQL `Getdate()` festgelegt. Beim Versuch, mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] einen neuen Datensatz einzufügen, wird der Wert auf `NULL` festgelegt. Erwartungsgemäß sollte der Wert auf den Datenbankstandard festgelegt werden.

A. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] behandelt diese Situation bei ID- (automatisch inkrementierten), ROWGUID- (von der Datenbank generierte GUID) und Timestamp-Spalten automatisch. In anderen Fällen sollten Sie <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` manuell festlegen und =<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> Eigenschaften <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>.

## <a name="multiple-dataloadoptions"></a>Mehrere DataLoadOptions

F. Können zusätzliche Ladeoptionen angegeben werden, ohne die erste zu überschreiben?

A. Ja. Die erste Option wird nicht überschrieben, wie im folgenden Beispiel veranschaulicht:

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a>Fehler bei der Verwendung von SQL Compact 3.5

F. Ich erhalte eine Fehlermeldung, wenn ich Tabellen aus einer SQL Server Compact 3,5-Datenbank ziehe.

A. Der objektrelationaler Designer unterstützt SQL Server Compact 3,5 nicht, obwohl die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit dies tut. In dieser Situation müssen Sie eigene Entitätsklassen erstellen und die entsprechenden Attribute hinzufügen.

## <a name="errors-in-inheritance-relationships"></a>Fehler in Vererbungsbeziehungen

F. Ich habe die Toolbox Vererbungs Form im objektrelationaler Designer verwendet, um zwei Entitäten zu verbinden, aber ich erhalte Fehler.

A. Es reicht nicht aus, die Beziehung zu erstellen. Sie müssen Informationen wie Unterscheidungsspalte, Basisklassen-Diskriminatorwert und Diskriminatorwert der abgeleiteten Klasse angeben.

## <a name="provider-model"></a>Anbietermodell

F. Ist ein öffentliches Anbietermodell verfügbar?

A. Es ist kein öffentliches Anbietermodell verfügbar. Zurzeit unterstützt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nur SQL Server und SQL Server Compact 3,5.

## <a name="sql-injection-attacks"></a>SQL-Injection-Angriffe

F. Wie wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vor SQL-Injection-Angriffen geschützt?

A. In herkömmlichen SQL-Abfragen, die durch die Verkettung der Benutzereingabe erzeugt wurden, stellte die SQL-Injection ein bedeutendes Risiko dar. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden solche Einfügungen durch die Verwendung von <xref:System.Data.SqlClient.SqlParameter> in Abfragen vermieden. Die Benutzereingabe wird in Parameterwerte umgewandelt. Auf diese Weise wird verhindert, dass böswillige Befehle aus Kundeneingaben verwendet werden.

## <a name="changing-read-only-flag-in-dbml-files"></a>Ändern des Schreibschutzflags in DBML-Dateien

F. Wie können Setter aus einigen Eigenschaften entfernt werden, wenn ein Objektmodell aus einer DBML-Datei erstellt wird?

A. Führen Sie für dieses erweiterte Szenario die folgenden Schritte aus:

1. Ändern Sie in der DBML-Datei die Eigenschaft, indem Sie das <xref:System.Data.Linq.ITable.IsReadOnly%2A>-Flag in `True` ändern.

2. Fügen Sie eine partielle Klasse hinzu. Erstellen Sie einen Konstruktor mit Parametern für die schreibgeschützten Member.

3. Überprüfen Sie den <xref:System.Data.Linq.Mapping.UpdateCheck>-Standardwert (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>), um zu bestimmen, ob dieses der richtige Wert für die Anwendung ist.

    > [!CAUTION]
    > Wenn Sie die objektrelationaler Designer in Visual Studio verwenden, werden die Änderungen möglicherweise überschrieben.

## <a name="aptca"></a>APTCA

F. Ist System.Data.Linq für die Verwendung durch teilweise vertrauenswürdigen Code markiert?

A. Ja, die System. Data. Linq. dll-Assembly gehört zu den .NET Framework Assemblys, die mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut gekennzeichnet sind. Ohne diese Markierung sind Assemblys in der .NET Framework nur zur Verwendung durch voll vertrauenswürdigen Code vorgesehen.

Das Prinzipal Szenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], um teilweise vertrauenswürdige Aufrufer zuzulassen, besteht darin, den Zugriff auf die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Assembly von Webanwendungen aus zu ermöglichen, bei denen die *Vertrauens* Konfiguration Mittel ist

## <a name="mapping-data-from-multiple-tables"></a>Zuordnen von Daten aus mehreren Tabellen

F. Die Daten in meiner Entität stammen aus mehreren Tabellen. Wie werden sie zugeordnet?

A. Sie können eine Ansicht in einer Datenbank erstellen und die Entität der Ansicht zuordnen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generiert für Ansichten dieselbe SQL wie für Tabellen.

> [!NOTE]
> Die Verwendung von Ansichten in diesem Szenario unterliegt Einschränkungen. Dieser Ansatz funktioniert am sichersten, wenn die für <xref:System.Data.Linq.Table%601> ausgeführten Vorgänge von der zugrunde liegenden Ansicht unterstützt werden. Nur Sie wissen, welche Vorgänge beabsichtigt sind. Die meisten Anwendungen sind z. b. schreibgeschützt, und eine weitere beträchtliche Zahl führt `Create`/`Update`/`Delete` Vorgänge nur mithilfe von gespeicherten Prozeduren für Sichten aus.

## <a name="connection-pooling"></a>Verbindungspooling

F. Gibt es ein Konstrukt, das das <xref:System.Data.Linq.DataContext>-Pooling unterstützt?

A. Sie sollten nicht versuchen, Instanzen von <xref:System.Data.Linq.DataContext> wiederzuverwenden. Jeder <xref:System.Data.Linq.DataContext> behält den Zustand (einschließlich eines Identitätscaches) für eine bestimmte Bearbeitungs-/Abfragesitzung bei. Um neue Instanzen auf Grundlage des aktuellen Zustands der Datenbank zu erhalten, verwenden Sie einen neuen <xref:System.Data.Linq.DataContext>.

Sie können weiterhin das zugrunde liegende ADO.net-Verbindungspooling verwenden. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../sql-server-connection-pooling.md).

## <a name="second-datacontext-is-not-updated"></a>Zweiter DataContext wird nicht aktualisiert

F. Zum Speichern von Werten in der Datenbank wurde eine Instanz von <xref:System.Data.Linq.DataContext> verwendet. Die aktualisierten Werte werden aber von einem zweiten <xref:System.Data.Linq.DataContext> in derselben Datenbank nicht angezeigt. Die zweite <xref:System.Data.Linq.DataContext>-Instanz scheint zwischengespeicherte Werte zurückzugeben.

A. Dieses Verhalten ist vorgesehen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gibt weiterhin dieselben Instanzen/Werte zurück, die in der ersten Instanz angezeigt wurden. Wenn Sie Updates vornehmen, verwenden Sie vollständige Parallelität. Die ursprünglichen Daten werden verwendet, um den aktuellen Datenbankzustand zu überprüfen und zu bestätigen, dass der Zustand weiterhin unverändert ist. Wenn er sich geändert hat, tritt ein Konflikt auf, der von der Anwendung gelöst werden muss. Eine Möglichkeit für die Anwendung besteht darin, den ursprünglichen Zustand auf den aktuellen Datenbankzustand zurückzusetzen und den Updateversuch zu wiederholen. Weitere Informationen finden Sie unter Gewusst [wie: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md).

Sie können auch <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf false festlegen, wodurch das Zwischenspeichern und Nachverfolgen von Änderungen deaktiviert wird. Anschließend können Sie bei jeder Abfrage die neuesten Werte abrufen.

## <a name="cannot-call-submitchanges-in-read-only-mode"></a>SubmitChanges kann nicht im schreibgeschützten Modus aufgerufen werden

F. Beim Versuch, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im schreibgeschützten Modus aufzurufen, tritt ein Fehler auf.

A. Im schreibgeschützten Modus ist der Kontext nicht mehr in der Lage, Änderungen nachzuverfolgen.

## <a name="see-also"></a>Siehe auch

- [Verweis](reference.md)
- [Problembehandlung](troubleshooting.md)
- [Sicherheit in LINQ to SQL](security-in-linq-to-sql.md)
