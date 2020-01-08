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
# <a name="frequently-asked-questions"></a><span data-ttu-id="b03f7-102">Häufig gestellte Fragen (FAQs)</span><span class="sxs-lookup"><span data-stu-id="b03f7-102">Frequently Asked Questions</span></span>

<span data-ttu-id="b03f7-103">In den folgenden Abschnitten werden einige häufige Probleme erläutert, die bei der Implementierung von LINQ auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b03f7-103">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="b03f7-104">Bei der [Problem](troubleshooting.md)Behandlung werden weitere Probleme behandelt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-104">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="b03f7-105">Verbindung kann nicht hergestellt werden</span><span class="sxs-lookup"><span data-stu-id="b03f7-105">Cannot Connect</span></span>

<span data-ttu-id="b03f7-106">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-106">Q.</span></span> <span data-ttu-id="b03f7-107">Es kann keine Verbindung mit meiner Datenbank hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-107">I cannot connect to my database.</span></span>

<span data-ttu-id="b03f7-108">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-108">A.</span></span> <span data-ttu-id="b03f7-109">Stellen Sie sicher, dass Ihre Verbindungs Zeichenfolge richtig ist und dass die SQL Server Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b03f7-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="b03f7-110">Beachten Sie auch, dass für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das Named Pipes-Protokoll aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="b03f7-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="b03f7-111">Weitere Informationen finden Sie unter [lernen durch](learning-by-walkthroughs.md)Exemplarische Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-111">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="b03f7-112">Änderungen an der Datenbank sind nicht vorhanden</span><span class="sxs-lookup"><span data-stu-id="b03f7-112">Changes to Database Lost</span></span>

<span data-ttu-id="b03f7-113">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-113">Q.</span></span> <span data-ttu-id="b03f7-114">Änderungen an den Daten in der Datenbank sind nicht mehr vorhanden, nachdem meine Anwendung erneut ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="b03f7-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="b03f7-115">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-115">A.</span></span> <span data-ttu-id="b03f7-116">Stellen Sie sicher, dass Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, um Ergebnisse in der Datenbank zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b03f7-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="b03f7-117">Wie lange kann die Datenbankverbindung geöffnet bleiben?</span><span class="sxs-lookup"><span data-stu-id="b03f7-117">Database Connection: Open How Long?</span></span>

<span data-ttu-id="b03f7-118">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-118">Q.</span></span> <span data-ttu-id="b03f7-119">Wie lange bleibt meine Datenbankverbindung geöffnet?</span><span class="sxs-lookup"><span data-stu-id="b03f7-119">How long does my database connection remain open?</span></span>

<span data-ttu-id="b03f7-120">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-120">A.</span></span> <span data-ttu-id="b03f7-121">Eine Verbindung bleibt normalerweise geöffnet, bis Sie die Abfrageergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="b03f7-122">Wenn Sie erwarten, dass die Verarbeitung sämtlicher Ergebnisse länger dauert und nichts dagegen spricht, die Ergebnisse zwischenzuspeichern, wenden Sie <xref:System.Linq.Enumerable.ToList%2A> auf die Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="b03f7-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="b03f7-123">In gängigen Szenarien, in denen jedes Objekt nur einmal verarbeitet wird, ist das Streamingmodell sowohl in `DataReader` als auch in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die bevorzugte Lösung.</span><span class="sxs-lookup"><span data-stu-id="b03f7-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="b03f7-124">Die genauen Details der Verbindungsnutzung hängen von folgenden Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="b03f7-124">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="b03f7-125">Verbindungsstatus, wenn <xref:System.Data.Linq.DataContext> mit einem Verbindungsobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b03f7-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="b03f7-126">Verbindungszeichenfolgen-Einstellungen (z. B. Aktivieren von MARS (Multiple Active Result Sets)).</span><span class="sxs-lookup"><span data-stu-id="b03f7-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="b03f7-127">Weitere Informationen finden Sie unter [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-127">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="b03f7-128">Ausführen von Updates ohne Abfrage</span><span class="sxs-lookup"><span data-stu-id="b03f7-128">Updating Without Querying</span></span>

<span data-ttu-id="b03f7-129">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-129">Q.</span></span> <span data-ttu-id="b03f7-130">Können Tabellendaten aktualisiert werden, ohne zuerst eine Datenbankabfrage auszuführen?</span><span class="sxs-lookup"><span data-stu-id="b03f7-130">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="b03f7-131">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-131">A.</span></span> <span data-ttu-id="b03f7-132">Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine mengenbasierten Updatebefehle bereitstellt, können Sie mithilfe einer der folgenden Techniken ohne vorherige Abfrage ein Update ausführen:</span><span class="sxs-lookup"><span data-stu-id="b03f7-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="b03f7-133">Verwenden Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>, um SQL-Code zu senden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="b03f7-134">Erstellen Sie eine neue Instanz des Objekts, und initialisieren Sie alle aktuellen Werte (Felder), die sich auf das Update auswirken.</span><span class="sxs-lookup"><span data-stu-id="b03f7-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="b03f7-135">Fügen Sie das Objekt anschließend mithilfe von <xref:System.Data.Linq.DataContext> an <xref:System.Data.Linq.Table%601.Attach%2A> an, und ändern Sie das gewünschte Feld.</span><span class="sxs-lookup"><span data-stu-id="b03f7-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="b03f7-136">Unerwartete Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="b03f7-136">Unexpected Query Results</span></span>

<span data-ttu-id="b03f7-137">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-137">Q.</span></span> <span data-ttu-id="b03f7-138">Meine Abfrage gibt unerwartete Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="b03f7-138">My query is returning unexpected results.</span></span> <span data-ttu-id="b03f7-139">Wie kann der Fehler festgestellt werden?</span><span class="sxs-lookup"><span data-stu-id="b03f7-139">How can I inspect what is occurring?</span></span>

<span data-ttu-id="b03f7-140">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b03f7-141">stellt mehrere Tools zum Überprüfen des generierten SQL-Codes bereit.</span><span class="sxs-lookup"><span data-stu-id="b03f7-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="b03f7-142">Eines der wichtigsten Tools ist <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="b03f7-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="b03f7-143">Weitere Informationen finden Sie [unter Debuggingunterstützung](debugging-support.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-143">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="b03f7-144">Gespeicherte Prozedur gibt unerwartete Ergebnisse zurück</span><span class="sxs-lookup"><span data-stu-id="b03f7-144">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="b03f7-145">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-145">Q.</span></span> <span data-ttu-id="b03f7-146">Der Rückgabewert einer gespeicherten Prozedur wird durch `MAX()` berechnet.</span><span class="sxs-lookup"><span data-stu-id="b03f7-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="b03f7-147">Wenn Sie die gespeicherte Prozedur auf die O/R-Designer-Oberfläche ziehen, ist der Rückgabewert nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="b03f7-147">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="b03f7-148">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b03f7-149">bietet zwei Möglichkeiten, von der Datenbank generierte Werte mithilfe gespeicherter Prozeduren zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="b03f7-149">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="b03f7-150">Durch Benennen des Ausgabeergebnisses.</span><span class="sxs-lookup"><span data-stu-id="b03f7-150">By naming the output result.</span></span>

- <span data-ttu-id="b03f7-151">Durch explizites Festlegen eines Ausgabeparameters.</span><span class="sxs-lookup"><span data-stu-id="b03f7-151">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="b03f7-152">Im Folgenden ein Beispiel für eine fehlerhafte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b03f7-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="b03f7-153">Da die Ergebnisse von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht zugeordnet werden können, wird immer 0 zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="b03f7-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="b03f7-154">Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der ein Ausgabeparameter verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b03f7-154">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="b03f7-155">Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der das Ausgabeergebnis benannt wird:</span><span class="sxs-lookup"><span data-stu-id="b03f7-155">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="b03f7-156">Weitere Informationen finden Sie unter [Anpassen von Vorgängen mithilfe von gespeicherten Prozeduren](customizing-operations-by-using-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-156">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="b03f7-157">Serialisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="b03f7-157">Serialization Errors</span></span>

<span data-ttu-id="b03f7-158">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-158">Q.</span></span> <span data-ttu-id="b03f7-159">Beim Versuch, die Serialisierung auszuführen, erhalte ich den folgenden Fehler: "Type ' System. Data. Linq. ChangeTracker + standardchangetracker '... ist nicht als serialisierbar gekennzeichnet. "</span><span class="sxs-lookup"><span data-stu-id="b03f7-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="b03f7-160">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-160">A.</span></span> <span data-ttu-id="b03f7-161">Die Codegenerierung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet Unterstützung für die <xref:System.Runtime.Serialization.DataContractSerializer>-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="b03f7-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="b03f7-162"><xref:System.Xml.Serialization.XmlSerializer> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="b03f7-163">Weitere Informationen finden Sie unter [Serialization (Serialisierung)](serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-163">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="b03f7-164">Mehrere DBML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b03f7-164">Multiple DBML Files</span></span>

<span data-ttu-id="b03f7-165">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-165">Q.</span></span> <span data-ttu-id="b03f7-166">Bei Verwendung mehrerer DBML-Dateien, die einige Tabellen gemeinsam nutzen, wird ein Compilerfehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b03f7-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="b03f7-167">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-167">A.</span></span> <span data-ttu-id="b03f7-168">Legen Sie die Eigenschaften für den **Kontext Namespace** und den **Entitäts Namespace** aus dem objektrelationaler Designer auf einen eindeutigen Wert für jede DBML-Datei fest.</span><span class="sxs-lookup"><span data-stu-id="b03f7-168">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="b03f7-169">Durch diese Lösung werden Konflikte zwischen Namen und Namespace vermieden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-169">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="b03f7-170">Vermeiden, dass von der Datenbank generierte Werte bei Einfüge- oder Updatevorgängen explizit festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="b03f7-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="b03f7-171">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-171">Q.</span></span> <span data-ttu-id="b03f7-172">Bei einer Datenbanktabelle mit einer `DateCreated`-Spalte wird die Spalte standardmäßig auf SQL `Getdate()` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="b03f7-173">Beim Versuch, mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] einen neuen Datensatz einzufügen, wird der Wert auf `NULL` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="b03f7-174">Erwartungsgemäß sollte der Wert auf den Datenbankstandard festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-174">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="b03f7-175">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b03f7-176">behandelt diese Situation bei ID- (automatisch inkrementierten), ROWGUID- (von der Datenbank generierte GUID) und Timestamp-Spalten automatisch.</span><span class="sxs-lookup"><span data-stu-id="b03f7-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="b03f7-177">In anderen Fällen sollten Sie <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` manuell festlegen und =<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> Eigenschaften <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>.</span><span class="sxs-lookup"><span data-stu-id="b03f7-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="b03f7-178">Mehrere DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="b03f7-178">Multiple DataLoadOptions</span></span>

<span data-ttu-id="b03f7-179">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-179">Q.</span></span> <span data-ttu-id="b03f7-180">Können zusätzliche Ladeoptionen angegeben werden, ohne die erste zu überschreiben?</span><span class="sxs-lookup"><span data-stu-id="b03f7-180">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="b03f7-181">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-181">A.</span></span> <span data-ttu-id="b03f7-182">Ja.</span><span class="sxs-lookup"><span data-stu-id="b03f7-182">Yes.</span></span> <span data-ttu-id="b03f7-183">Die erste Option wird nicht überschrieben, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b03f7-183">The first is not overwritten, as in the following example:</span></span>

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

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="b03f7-184">Fehler bei der Verwendung von SQL Compact 3.5</span><span class="sxs-lookup"><span data-stu-id="b03f7-184">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="b03f7-185">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-185">Q.</span></span> <span data-ttu-id="b03f7-186">Ich erhalte eine Fehlermeldung, wenn ich Tabellen aus einer SQL Server Compact 3,5-Datenbank ziehe.</span><span class="sxs-lookup"><span data-stu-id="b03f7-186">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="b03f7-187">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-187">A.</span></span> <span data-ttu-id="b03f7-188">Der objektrelationaler Designer unterstützt SQL Server Compact 3,5 nicht, obwohl die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit dies tut.</span><span class="sxs-lookup"><span data-stu-id="b03f7-188">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="b03f7-189">In dieser Situation müssen Sie eigene Entitätsklassen erstellen und die entsprechenden Attribute hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="b03f7-190">Fehler in Vererbungsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="b03f7-190">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="b03f7-191">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-191">Q.</span></span> <span data-ttu-id="b03f7-192">Ich habe die Toolbox Vererbungs Form im objektrelationaler Designer verwendet, um zwei Entitäten zu verbinden, aber ich erhalte Fehler.</span><span class="sxs-lookup"><span data-stu-id="b03f7-192">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="b03f7-193">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-193">A.</span></span> <span data-ttu-id="b03f7-194">Es reicht nicht aus, die Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="b03f7-195">Sie müssen Informationen wie Unterscheidungsspalte, Basisklassen-Diskriminatorwert und Diskriminatorwert der abgeleiteten Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="b03f7-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="b03f7-196">Anbietermodell</span><span class="sxs-lookup"><span data-stu-id="b03f7-196">Provider Model</span></span>

<span data-ttu-id="b03f7-197">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-197">Q.</span></span> <span data-ttu-id="b03f7-198">Ist ein öffentliches Anbietermodell verfügbar?</span><span class="sxs-lookup"><span data-stu-id="b03f7-198">Is a public provider model available?</span></span>

<span data-ttu-id="b03f7-199">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-199">A.</span></span> <span data-ttu-id="b03f7-200">Es ist kein öffentliches Anbietermodell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b03f7-200">No public provider model is available.</span></span> <span data-ttu-id="b03f7-201">Zurzeit unterstützt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nur SQL Server und SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="b03f7-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="b03f7-202">SQL-Injection-Angriffe</span><span class="sxs-lookup"><span data-stu-id="b03f7-202">SQL-Injection Attacks</span></span>

<span data-ttu-id="b03f7-203">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-203">Q.</span></span> <span data-ttu-id="b03f7-204">Wie wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vor SQL-Injection-Angriffen geschützt?</span><span class="sxs-lookup"><span data-stu-id="b03f7-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="b03f7-205">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-205">A.</span></span> <span data-ttu-id="b03f7-206">In herkömmlichen SQL-Abfragen, die durch die Verkettung der Benutzereingabe erzeugt wurden, stellte die SQL-Injection ein bedeutendes Risiko dar.</span><span class="sxs-lookup"><span data-stu-id="b03f7-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> <span data-ttu-id="b03f7-207">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden solche Einfügungen durch die Verwendung von <xref:System.Data.SqlClient.SqlParameter> in Abfragen vermieden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-207">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="b03f7-208">Die Benutzereingabe wird in Parameterwerte umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-208">User input is turned into parameter values.</span></span> <span data-ttu-id="b03f7-209">Auf diese Weise wird verhindert, dass böswillige Befehle aus Kundeneingaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-209">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="b03f7-210">Ändern des Schreibschutzflags in DBML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b03f7-210">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="b03f7-211">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-211">Q.</span></span> <span data-ttu-id="b03f7-212">Wie können Setter aus einigen Eigenschaften entfernt werden, wenn ein Objektmodell aus einer DBML-Datei erstellt wird?</span><span class="sxs-lookup"><span data-stu-id="b03f7-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="b03f7-213">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-213">A.</span></span> <span data-ttu-id="b03f7-214">Führen Sie für dieses erweiterte Szenario die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b03f7-214">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="b03f7-215">Ändern Sie in der DBML-Datei die Eigenschaft, indem Sie das <xref:System.Data.Linq.ITable.IsReadOnly%2A>-Flag in `True` ändern.</span><span class="sxs-lookup"><span data-stu-id="b03f7-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="b03f7-216">Fügen Sie eine partielle Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="b03f7-216">Add a partial class.</span></span> <span data-ttu-id="b03f7-217">Erstellen Sie einen Konstruktor mit Parametern für die schreibgeschützten Member.</span><span class="sxs-lookup"><span data-stu-id="b03f7-217">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="b03f7-218">Überprüfen Sie den <xref:System.Data.Linq.Mapping.UpdateCheck>-Standardwert (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>), um zu bestimmen, ob dieses der richtige Wert für die Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="b03f7-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b03f7-219">Wenn Sie die objektrelationaler Designer in Visual Studio verwenden, werden die Änderungen möglicherweise überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b03f7-219">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="b03f7-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="b03f7-220">APTCA</span></span>

<span data-ttu-id="b03f7-221">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-221">Q.</span></span> <span data-ttu-id="b03f7-222">Ist System.Data.Linq für die Verwendung durch teilweise vertrauenswürdigen Code markiert?</span><span class="sxs-lookup"><span data-stu-id="b03f7-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="b03f7-223">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-223">A.</span></span> <span data-ttu-id="b03f7-224">Ja, die System. Data. Linq. dll-Assembly gehört zu den .NET Framework Assemblys, die mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="b03f7-224">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="b03f7-225">Ohne diese Markierung sind Assemblys in der .NET Framework nur zur Verwendung durch voll vertrauenswürdigen Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-225">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="b03f7-226">Das Prinzipal Szenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], um teilweise vertrauenswürdige Aufrufer zuzulassen, besteht darin, den Zugriff auf die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Assembly von Webanwendungen aus zu ermöglichen, bei denen die *Vertrauens* Konfiguration Mittel ist</span><span class="sxs-lookup"><span data-stu-id="b03f7-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="b03f7-227">Zuordnen von Daten aus mehreren Tabellen</span><span class="sxs-lookup"><span data-stu-id="b03f7-227">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="b03f7-228">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-228">Q.</span></span> <span data-ttu-id="b03f7-229">Die Daten in meiner Entität stammen aus mehreren Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="b03f7-230">Wie werden sie zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="b03f7-230">How do I map it?</span></span>

<span data-ttu-id="b03f7-231">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-231">A.</span></span> <span data-ttu-id="b03f7-232">Sie können eine Ansicht in einer Datenbank erstellen und die Entität der Ansicht zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b03f7-233">generiert für Ansichten dieselbe SQL wie für Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-233">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="b03f7-234">Die Verwendung von Ansichten in diesem Szenario unterliegt Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="b03f7-235">Dieser Ansatz funktioniert am sichersten, wenn die für <xref:System.Data.Linq.Table%601> ausgeführten Vorgänge von der zugrunde liegenden Ansicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="b03f7-236">Nur Sie wissen, welche Vorgänge beabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="b03f7-236">Only you know which operations are intended.</span></span> <span data-ttu-id="b03f7-237">Die meisten Anwendungen sind z. b. schreibgeschützt, und eine weitere beträchtliche Zahl führt `Create`/`Update`/`Delete` Vorgänge nur mithilfe von gespeicherten Prozeduren für Sichten aus.</span><span class="sxs-lookup"><span data-stu-id="b03f7-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="b03f7-238">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="b03f7-238">Connection Pooling</span></span>

<span data-ttu-id="b03f7-239">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-239">Q.</span></span> <span data-ttu-id="b03f7-240">Gibt es ein Konstrukt, das das <xref:System.Data.Linq.DataContext>-Pooling unterstützt?</span><span class="sxs-lookup"><span data-stu-id="b03f7-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="b03f7-241">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-241">A.</span></span> <span data-ttu-id="b03f7-242">Sie sollten nicht versuchen, Instanzen von <xref:System.Data.Linq.DataContext> wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="b03f7-243">Jeder <xref:System.Data.Linq.DataContext> behält den Zustand (einschließlich eines Identitätscaches) für eine bestimmte Bearbeitungs-/Abfragesitzung bei.</span><span class="sxs-lookup"><span data-stu-id="b03f7-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="b03f7-244">Um neue Instanzen auf Grundlage des aktuellen Zustands der Datenbank zu erhalten, verwenden Sie einen neuen <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="b03f7-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="b03f7-245">Sie können weiterhin das zugrunde liegende ADO.net-Verbindungspooling verwenden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-245">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="b03f7-246">Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="b03f7-247">Zweiter DataContext wird nicht aktualisiert</span><span class="sxs-lookup"><span data-stu-id="b03f7-247">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="b03f7-248">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-248">Q.</span></span> <span data-ttu-id="b03f7-249">Zum Speichern von Werten in der Datenbank wurde eine Instanz von <xref:System.Data.Linq.DataContext> verwendet.</span><span class="sxs-lookup"><span data-stu-id="b03f7-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="b03f7-250">Die aktualisierten Werte werden aber von einem zweiten <xref:System.Data.Linq.DataContext> in derselben Datenbank nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b03f7-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="b03f7-251">Die zweite <xref:System.Data.Linq.DataContext>-Instanz scheint zwischengespeicherte Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b03f7-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="b03f7-252">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-252">A.</span></span> <span data-ttu-id="b03f7-253">Dieses Verhalten ist vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b03f7-254">gibt weiterhin dieselben Instanzen/Werte zurück, die in der ersten Instanz angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="b03f7-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="b03f7-255">Wenn Sie Updates vornehmen, verwenden Sie vollständige Parallelität.</span><span class="sxs-lookup"><span data-stu-id="b03f7-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="b03f7-256">Die ursprünglichen Daten werden verwendet, um den aktuellen Datenbankzustand zu überprüfen und zu bestätigen, dass der Zustand weiterhin unverändert ist.</span><span class="sxs-lookup"><span data-stu-id="b03f7-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="b03f7-257">Wenn er sich geändert hat, tritt ein Konflikt auf, der von der Anwendung gelöst werden muss.</span><span class="sxs-lookup"><span data-stu-id="b03f7-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="b03f7-258">Eine Möglichkeit für die Anwendung besteht darin, den ursprünglichen Zustand auf den aktuellen Datenbankzustand zurückzusetzen und den Updateversuch zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="b03f7-259">Weitere Informationen finden Sie unter Gewusst [wie: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="b03f7-259">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="b03f7-260">Sie können auch <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf false festlegen, wodurch das Zwischenspeichern und Nachverfolgen von Änderungen deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b03f7-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="b03f7-261">Anschließend können Sie bei jeder Abfrage die neuesten Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-261">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="b03f7-262">SubmitChanges kann nicht im schreibgeschützten Modus aufgerufen werden</span><span class="sxs-lookup"><span data-stu-id="b03f7-262">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="b03f7-263">F.</span><span class="sxs-lookup"><span data-stu-id="b03f7-263">Q.</span></span> <span data-ttu-id="b03f7-264">Beim Versuch, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im schreibgeschützten Modus aufzurufen, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b03f7-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="b03f7-265">A.</span><span class="sxs-lookup"><span data-stu-id="b03f7-265">A.</span></span> <span data-ttu-id="b03f7-266">Im schreibgeschützten Modus ist der Kontext nicht mehr in der Lage, Änderungen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b03f7-266">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="b03f7-267">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b03f7-267">See also</span></span>

- [<span data-ttu-id="b03f7-268">Verweis</span><span class="sxs-lookup"><span data-stu-id="b03f7-268">Reference</span></span>](reference.md)
- [<span data-ttu-id="b03f7-269">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="b03f7-269">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="b03f7-270">Sicherheit in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b03f7-270">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
