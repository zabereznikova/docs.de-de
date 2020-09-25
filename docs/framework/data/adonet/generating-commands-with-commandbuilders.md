---
title: Generieren von Befehlen mit CommandBuilder-Objekten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
ms.openlocfilehash: d88f5772e038766d49baf8c758c547e6d5667904
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200718"
---
# <a name="generating-commands-with-commandbuilders"></a>Generieren von Befehlen mit CommandBuilder-Objekten

Wenn die `SelectCommand`-Eigenschaft dynamisch zur Laufzeit angegeben wird, z. B. mit einem Abfragetool, in dem der Benutzer einen Textbefehl eingibt, sind Sie zur Entwurfszeit u. U. nicht in der Lage, den entsprechenden `InsertCommand`, `UpdateCommand` oder `DeleteCommand` anzugeben. Wenn Ihre <xref:System.Data.DataTable> einer einzelnen Datenbanktabelle zugeordnet ist oder aus einer solchen generiert wurde, können Sie mithilfe des <xref:System.Data.Common.DbCommandBuilder>-Objekts automatisch den `DeleteCommand`, den `InsertCommand` und den `UpdateCommand` des <xref:System.Data.Common.DbDataAdapter> generieren.  
  
 Damit die automatische Befehlsgenerierung funktioniert, muss mindestens die `SelectCommand`-Eigenschaft festgelegt werden. Das durch die `SelectCommand`-Eigenschaft abgerufene Tabellenschema bestimmt die Syntax der automatisch generierten INSERT-, UPDATE- und DELETE-Anweisungen.  
  
 Der <xref:System.Data.Common.DbCommandBuilder> muss `SelectCommand` ausführen, damit die zum Konstruieren der SQL-Befehle INSERT, UPDATE und DELETE erforderlichen Metadaten zurückgegeben werden. Daher ist ein erneutes Lesen der Datenquelle erforderlich, was die Leistung herabsetzen kann. Eine optimale Leistung lässt sich erzielen, indem Sie die Befehle direkt angeben, anstatt den <xref:System.Data.Common.DbCommandBuilder> zu verwenden.  
  
 Der `SelectCommand` muss außerdem mindestens einen Primärschlüssel oder eine eindeutige Spalte zurückgeben. Wenn weder das eine noch das andere vorhanden ist, wird eine `InvalidOperation`-Ausnahme ausgelöst, und die Befehle werden nicht generiert.  
  
 Bei einer Zuordnung zu einem `DataAdapter` generiert der <xref:System.Data.Common.DbCommandBuilder> automatisch die Eigenschaften `InsertCommand`, `UpdateCommand` und `DeleteCommand` des `DataAdapter`, sofern es sich um NULL-Verweise handelt. Wenn für eine Eigenschaft bereits ein `Command` vorhanden ist, wird der vorhandene `Command` verwendet.  
  
 Datenbankansichten, die durch das Verknüpfen von zwei oder mehr Datenbanken erstellt wurden, werden nicht als eine einzelne Datenbanktabelle betrachtet. In dieser Instanz können Sie den <xref:System.Data.Common.DbCommandBuilder> nicht zum automatischen Generieren von Befehlen verwenden; Sie müssen die Befehle explizit angeben. Weitere Informationen zum expliziten Festlegen von Befehlen zum Auflösen von Aktualisierungen für eine `DataSet` wieder in die Datenquelle finden Sie unter [Aktualisieren von Datenquellen mit DataAdapters](updating-data-sources-with-dataadapters.md).  
  
 Unter Umständen möchten Sie der aktualisierten Zeile eines `DataSet` erneut Ausgabeparameter zuordnen. Eine allgemeine Aufgabe wäre das Abrufen des Werts eines automatisch generierten Identitätsfelds oder Timestamps aus der Datenquelle. Standardmäßig werden den Spalten in einer aktualisierten Zeile vom <xref:System.Data.Common.DbCommandBuilder> keine Ausgabeparameter zugeordnet. In diesem Fall müssen Sie den Befehl explizit angeben. Ein Beispiel für die Zuordnung eines automatisch generierten Identitäts Felds zu einer Spalte einer eingefügten Zeile finden Sie unter [Abrufen von Identitäts-oder](retrieving-identity-or-autonumber-values.md)Auto Sequenz Werten.  
  
## <a name="rules-for-automatically-generated-commands"></a>Regeln für automatisch generierte Befehle  

 Die folgende Tabelle enthält die Regeln für das Generieren von automatisch generierten Befehlen.  
  
|Get-Help|Regel|  
|-------------|----------|  
|`InsertCommand`|Fügt in der Datenquelle für alle Zeilen in der Tabelle, die den <xref:System.Data.DataRow.RowState%2A><xref:System.Data.DataRowState.Added> aufweisen, eine Zeile ein. Fügt Werte für alle Spalten ein, die aktualisiert werden können (jedoch nicht für Spalten wie Identitäten, Ausdrücke oder Timestamps).|  
|`UpdateCommand`|Aktualisiert Zeilen in der Datenquelle für alle Zeilen in der Tabelle, die den `RowState`-Wert <xref:System.Data.DataRowState.Modified> aufweisen. Aktualisiert die Werte aller Spalten mit Ausnahme von Spalten, die nicht aktualisiert werden können, z. B. Identitäten oder Ausdrücke. Aktualisiert alle Zeilen, deren Spaltenwerte in der Datenquelle den Primärschlüssel-Spaltenwerten der Zeile entsprechen und bei denen die übrigen Spalten in der Datenquelle den ursprünglichen Werten der Zeile entsprechen. Weitere Informationen finden Sie unter "Vollständiges Parallelitätsmodell für Updates und Löschvorgänge" weiter unten in diesem Thema.|  
|`DeleteCommand`|Löscht Zeilen in der Datenquelle für alle Zeilen in der Tabelle, die den `RowState`-Wert <xref:System.Data.DataRowState.Deleted> aufweisen. Löscht alle Zeilen, deren Spaltenwerte den Primärschlüssel-Spaltenwerten der Zeile entsprechen und bei denen die übrigen Spalten in der Datenquelle den ursprünglichen Werten der Zeile entsprechen. Weitere Informationen finden Sie unter "Vollständiges Parallelitätsmodell für Updates und Löschvorgänge" weiter unten in diesem Thema.|  
  
## <a name="optimistic-concurrency-model-for-updates-and-deletes"></a>Vollständiges Parallelitätsmodell für Updates und Löschvorgänge  

 Die Logik zum automatischen Erstellen von Befehlen für Update-und *Delete-Anweisungen*basiert auf der vollständigen Parallelität, d. h., Datensätze sind nicht für die Bearbeitung gesperrt und können jederzeit von anderen Benutzern oder Prozessen geändert werden. Da ein Datensatz nach der Rückgabe aus der SELECT-Anweisung und vor der Ausführung der UPDATE- oder DELETE-Anweisung ggf. geändert wurde, enthält die automatisch generierte UPDATE- oder DELETE-Anweisung eine WHERE-Klausel, die angibt, dass eine Zeile nur dann aktualisiert wird, wenn sie alle ursprünglichen Werte enthält und nicht aus der Datenquelle gelöscht wurde. Hierdurch wird vermieden, dass neue Daten überschrieben werden. In Fällen, in denen ein automatisch generierter Updatebefehl versucht, eine Zeile zu aktualisieren, die gelöscht wurde oder nicht die ursprünglichen Werte im <xref:System.Data.DataSet> enthält, hat der Befehl keine Auswirkungen auf Datensätze, und es wird eine <xref:System.Data.DBConcurrencyException> ausgelöst.  
  
 Wenn UPDATE oder DELETE unabhängig von den ursprünglichen Werten ausgeführt werden sollen, muss der `UpdateCommand` für den `DataAdapter` explizit festgelegt und die automatische Befehlsgenerierung damit außer Kraft gesetzt werden.  
  
## <a name="limitations-of-automatic-command-generation-logic"></a>Einschränkungen der Logik für die automatische Generierung von Befehlen  

 Folgende Einschränkungen gelten für die automatische Generierung von Befehlen.  
  
### <a name="unrelated-tables-only"></a>Nur nicht verknüpfte Tabellen  

 Die Logik für die automatische Generierung von Befehlen generiert INSERT-, UPDATE- oder DELETE-Befehle für eigenständige Tabellen, wobei Verknüpfungen mit anderen Tabellen in der Datenquelle unberücksichtigt bleiben. Daher kann ein Fehler auftreten, wenn Sie `Update` aufrufen, um Änderungen an einer Spalte zu übermitteln, die in der Datenbank Fremdschlüsseleinschränkungen unterworfen ist. Sie können diese Ausnahme vermeiden, indem Sie zum Aktualisieren von Spalten, die einer Einschränkung eines Fremdschlüssels unterworfen sind, nicht den <xref:System.Data.Common.DbCommandBuilder> verwenden, sondern die Anweisungen zur Durchführung der Operation explizit angeben.  
  
### <a name="table-and-column-names"></a>Tabellennamen und Spaltennamen  

 Die Logik für die automatische Befehlsgenerierung kann fehlschlagen, wenn Spalten- oder Tabellennamen Sonderzeichen wie Leerzeichen, Punkte, Anführungszeichen oder andere nicht alphanumerische Zeichen enthalten, selbst wenn diese durch Klammern getrennt sind. Leerzeichen können je nach Anbieter von der Generierungslogik durch Festlegen des QuotePrefix-Parameters und QuoteSuffix-Parameters möglicherweise verarbeitet werden, Sonderzeichen können jedoch nicht mit Escapezeichen versehen werden. Voll qualifizierte Tabellennamen in Form von *catalog. Schema. Table* werden unterstützt.  
  
## <a name="using-the-commandbuilder-to-automatically-generate-an-sql-statement"></a>Verwenden des CommandBuilder-Objekts zum automatischen Generieren einer SQL-Anweisung  

 Legen Sie zum automatischen Generieren von SQL-Anweisungen für einen `DataAdapter` zuerst die `SelectCommand`-Eigenschaft des `DataAdapter` fest. Erstellen Sie dann ein `CommandBuilder`-Objekt, und geben Sie als Argument den `DataAdapter` an, für den der `CommandBuilder` automatisch SQL-Anweisungen generieren soll.  
  
```vb  
' Assumes that connection is a valid SqlConnection object
' inside of a Using block.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", connection)  
Dim builder As SqlCommandBuilder = New SqlCommandBuilder(adapter)  
builder.QuotePrefix = "["  
builder.QuoteSuffix = "]"  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object  
// inside of a using block.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", connection);  
SqlCommandBuilder builder = new SqlCommandBuilder(adapter);  
builder.QuotePrefix = "[";  
builder.QuoteSuffix = "]";  
```  
  
## <a name="modifying-the-selectcommand"></a>Ändern von SelectCommand  

 Wenn Sie den `CommandText` von `SelectCommand` ändern, nachdem die Befehle INSERT, UPDATE oder DELETE automatisch generiert wurden, kann eine Ausnahme auftreten. Wenn der geänderte `SelectCommand.CommandText` Schemainformationen enthält, die nicht mit dem `SelectCommand.CommandText` zum Zeitpunkt der automatischen Generierung der Befehle INSERT, UPDATE oder DELETE konsistent sind, wird bei späteren Aufrufen der `DataAdapter.Update`-Methode möglicherweise versucht, auf Spalten zuzugreifen, die nicht mehr in der aktuellen Tabelle vorhanden sind, auf die `SelectCommand` verweist. In diesem Fall wird eine Ausnahme ausgelöst.  
  
 Sie können die vom `CommandBuilder` zum automatischen Generieren von Befehlen verwendeten Schemainformationen aktualisieren, indem Sie die `RefreshSchema`-Methode des `CommandBuilder` aufrufen.  
  
 Wenn Sie wissen möchten, welcher Befehl automatisch generiert wurde, können Sie mit den Methoden `GetInsertCommand`, `GetUpdateCommand` und `GetDeleteCommand` des `CommandBuilder`-Objekts Verweise auf die Befehle abrufen und die `CommandText`-Eigenschaft des zugeordneten Befehls überprüfen.  
  
 Im folgenden Codebeispiel wird der automatisch generierte UPDATE-Befehl in die Konsole geschrieben.  
  
```vb
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```

```csharp
Console.WriteLine(builder.GetUpdateCommand().CommandText);
```
  
 Das folgende Beispiel erstellt die `Customers`-Tabelle im `custDS`-Dataset neu. Die Refresh **Schema** -Methode wird aufgerufen, um die automatisch generierten Befehle mit diesen neuen Spalten Informationen zu aktualisieren.  
  
```vb  
' Assumes an open SqlConnection and SqlDataAdapter inside of a Using block.  
adapter.SelectCommand.CommandText = _  
  "SELECT CustomerID, ContactName FROM dbo.Customers"  
builder.RefreshSchema()  
  
custDS.Tables.Remove(custDS.Tables("Customers"))  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
// Assumes an open SqlConnection and SqlDataAdapter inside of a using block.  
adapter.SelectCommand.CommandText =
  "SELECT CustomerID, ContactName FROM dbo.Customers";  
builder.RefreshSchema();  
  
custDS.Tables.Remove(custDS.Tables["Customers"]);  
adapter.Fill(custDS, "Customers");  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Befehle und Parameter](commands-and-parameters.md)
- [Ausführen eines Befehls](executing-a-command.md)
- ["DbConnection", "DbCommand" und "DbException"](dbconnection-dbcommand-and-dbexception.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
