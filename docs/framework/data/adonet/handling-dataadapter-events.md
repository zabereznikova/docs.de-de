---
title: Behandeln von DataAdapter-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: d01198d158c4e1c64f12e8a0756c3d4e599fce74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149543"
---
# <a name="handling-dataadapter-events"></a>Behandeln von DataAdapter-Ereignissen
Der ADO.NET-<xref:System.Data.Common.DataAdapter> macht drei Ereignisse verfügbar, mit denen Sie auf Änderungen der Daten der Datenquelle reagieren können. In der folgenden Tabelle finden Sie eine Beschreibung dieser `DataAdapter`-Ereignisse.  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|`RowUpdating`|Es wird gerade ein Aktualisierungs-, Einfüge- oder Löschvorgang für eine Zeile eingeleitet (durch Aufrufen einer der `Update`-Methoden).|  
|`RowUpdated`|Ein Update-, Einfüge- oder Löschvorgang für eine Zeile ist abgeschlossen (durch Aufrufen einer der `Update`-Methoden).|  
|`FillError`|Während eines `Fill`-Vorgangs ist ein Fehler aufgetreten.|  
  
## <a name="rowupdating-and-rowupdated"></a>RowUpdating und RowUpdated  
 `RowUpdating` wird ausgelöst, bevor ein Update einer Zeile des <xref:System.Data.DataSet>-Objekts in der Datenquelle verarbeitet wurde. `RowUpdated` wird ausgelöst, nachdem ein Update einer Zeile des `DataSet`-Objekts in der Datenquelle verarbeitet wurde. Folglich können Sie mit dem `RowUpdating`-Ereignis das Verhalten von Updates ändern, bevor sie vorgenommen werden, zusätzliche Behandlungsoptionen beim Auftreten eines Updates anbieten, einen Verweis auf eine aktualisierte Zeile beibehalten, das aktuelle Update abbrechen und es für die spätere Verarbeitung in einem Stapelverarbeitungsprozess einplanen usw. `RowUpdated` ist hilfreich bei der Reaktion auf Fehler und Ausnahmen, die während des Updates auftreten. Sie können dem `DataSet` Fehlerinformationen, eine Wiederholungslogik u. a. m. hinzufügen.  
  
 Die Argumente <xref:System.Data.Common.RowUpdatingEventArgs> und <xref:System.Data.Common.RowUpdatedEventArgs>, die an die Ereignisse `RowUpdating` und `RowUpdated` übergeben werden, enthalten Folgendes: eine `Command`-Eigenschaft, die auf das `Command`-Objekt verweist, das zur Ausführung des Updates verwendet wird, eine `Row`-Eigenschaft, die auf das `DataRow`-Objekt verweist, dass die aktualisierten Informationen enthält, eine `StatementType`-Eigenschaft zur Angabe der auszuführenden Updatestypen, die `TableMapping`, sofern zutreffend, und den `Status` des Vorgangs.  
  
 Mit der `Status`-Eigenschaft können Sie ermitteln, ob während des Vorgangs ein Fehler aufgetreten ist, und gegebenenfalls die Aktionen für die aktuellen und die resultierenden Zeilen steuern. Wenn das Ereignis eintritt, entspricht die `Status`-Eigenschaft entweder `Continue` oder `ErrorsOccurred`. In der folgenden Tabelle sind die Werte dargestellt, die Sie für die `Status`-Eigenschaft festlegen können, um nachfolgende Aktionen während des Updates zu steuern.  
  
|Status|Beschreibung|  
|------------|-----------------|  
|`Continue`|Setzt den Aktualisierungsvorgang fort.|  
|`ErrorsOccurred`|Bricht den Updatevorgang ab und löst eine Ausnahme aus.|  
|`SkipCurrentRow`|Ignoriert die aktuelle Zeile und setzt den Aktualisierungsvorgang fort.|  
|`SkipAllRemainingRows`|Bricht den Aktualisierungsvorgang ab, löst jedoch keine Ausnahme aus.|  
  
 Durch das Festlegen der `Status`-Eigenschaft auf `ErrorsOccurred` wird eine Ausnahme ausgelöst. Welche Ausnahme ausgelöst wird, können Sie steuern, indem Sie für die `Errors`-Eigenschaft die gewünschte Ausnahme angeben. Wenn Sie einen der anderen Werte für `Status` verwenden, wird keine Ausnahme ausgelöst.  
  
 Sie können auch die `ContinueUpdateOnError`-Eigenschaft verwenden, um Fehler für aktualisierte Zeilen zu behandeln. Wenn für `DataAdapter.ContinueUpdateOnError` der Wert `true` angegeben ist und das Updates einer Zeile eine Ausnahme auslöst, wird der Text der Ausnahme in die `RowError`-Information der entsprechenden Zeile aufgenommen. Die Verarbeitung wird fortgesetzt, ohne dass eine Ausnahme ausgelöst wird. Auf diese Weise können Sie auf Fehler reagieren, wenn `Update` abgeschlossen wurde. Dagegen können Sie beim `RowUpdated`-Ereignis auf den Fehler reagieren, sobald er festgestellt wird.  
  
 Im folgenden Codebeispiel wird dargestellt, wie Ereignishandler hinzugefügt und entfernt werden. Der `RowUpdating`-Ereignishandler schreibt ein Protokoll aller gelöschten Datensätze und versieht die Löschvorgangaufzeichnungen jeweils mit einem Timestamp. Der `RowUpdated` Ereignishandler fügt der `RowError` Eigenschaft der Zeile `DataSet`in der Fehlerinformationen hinzu, unterdrückt die `ContinueUpdateOnError`  =  `true`Ausnahme und setzt die Verarbeitung fort (Spiegelung des Verhaltens von ).  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
' Add handlers.  
AddHandler custAdapter.RowUpdating, New SqlRowUpdatingEventHandler( _  
  AddressOf OnRowUpdating)  
AddHandler custAdapter.RowUpdated, New SqlRowUpdatedEventHandler(  
  AddressOf OnRowUpdated)  
  
' Set DataAdapter command properties, fill DataSet, and modify DataSet.  
  
custAdapter.Update(custDS, "Customers")  
  
' Remove handlers.  
RemoveHandler custAdapter.RowUpdating, _  
  New SqlRowUpdatingEventHandler(AddressOf OnRowUpdating)  
RemoveHandler custAdapter.RowUpdated, _  
  New SqlRowUpdatedEventHandler(AddressOf OnRowUpdated)  
  
Private Shared Sub OnRowUpdating(sender As Object, _  
  args As SqlRowUpdatingEventArgs)  
  If args.StatementType = StatementType.Delete Then  
    Dim tw As System.IO.TextWriter = _  
  System.IO.File.AppendText("Deletes.log")  
    tw.WriteLine( _  
      "{0}: Customer {1} Deleted.", DateTime.Now, args.Row(_  
      "CustomerID", DataRowVersion.Original))  
    tw.Close()  
  End If  
End Sub  
  
Private Shared Sub OnRowUpdated( _  
  sender As Object, args As SqlRowUpdatedEventArgs)  
  If args.Status = UpdateStatus.ErrorsOccurred  
    args.Status = UpdateStatus.SkipCurrentRow  
    args.Row.RowError = args.Errors.Message  
  End If  
End Sub  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
// Add handlers.  
custAdapter.RowUpdating += new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
// Set DataAdapter command properties, fill DataSet, modify DataSet.  
  
custAdapter.Update(custDS, "Customers");  
  
// Remove handlers.  
custAdapter.RowUpdating -= new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated -= new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
protected static void OnRowUpdating(  
  object sender, SqlRowUpdatingEventArgs args)  
{  
  if (args.StatementType == StatementType.Delete)  
  {  
    System.IO.TextWriter tw = System.IO.File.AppendText("Deletes.log");  
    tw.WriteLine(  
      "{0}: Customer {1} Deleted.", DateTime.Now,
       args.Row["CustomerID", DataRowVersion.Original]);  
    tw.Close();  
  }  
}  
  
protected static void OnRowUpdated(  
  object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.Status == UpdateStatus.ErrorsOccurred)  
  {  
    args.Row.RowError = args.Errors.Message;  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="fillerror"></a>FillError  
 Der `DataAdapter` gibt das `FillError`-Ereignis aus, wenn während des `Fill`-Vorgangs ein Fehler auftritt. Dieser Fehlertyp tritt auf, wenn die Daten in der hinzugefügten Zeile nicht ohne Präzisionsverlust in einen .NET Framework-Typ konvertiert werden konnten.  
  
 Wenn während eines `Fill`-Vorgangs ein Fehler auftritt, wird der `DataTable` die aktuelle Zeile nicht hinzugefügt. Mit dem `FillError`-Ereignis können Sie den Fehler auflösen und die Zeile hinzufügen oder die betreffende Zeile ignorieren und den `Fill`-Vorgang fortsetzen.  
  
 Die an das `FillErrorEventArgs`-Ereignis übergebenen `FillError` können mehrere Eigenschaften enthalten, mit denen Sie auf Fehler reagieren und diese auflösen können. In der folgenden Tabelle werden die Eigenschaften des `FillErrorEventArgs`-Objekts dargestellt.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|`Errors`|Die `Exception`, die aufgetreten ist.|  
|`DataTable`|Das `DataTable`-Objekt, das ausgefüllt wurde, als der Fehler auftrat.|  
|`Values`|Ein Array aus Objekten, das die Werte der beim Eintreten des Fehlers hinzugefügten Zeile enthält. Die Ordinalzahlverweise des `Values`-Arrays entsprechen den Ordinalzahlverweisen der Spalten der hinzugefügten Zeile. So ist z. B. `Values[0]` der Wert, der als erste Spalte der Zeile hinzugefügt wurde.|  
|`Continue`|Sie können festlegen, ob eine Ausnahme ausgelöst werden soll oder nicht. Durch das Festlegen der `Continue`-Eigenschaft auf `false` wird der aktuelle `Fill`-Vorgang angehalten, und es wird eine Ausnahme ausgelöst. Durch das Festlegen der `Continue`-Eigenschaft auf `true` wird der `Fill`-Vorgang trotz des Fehlers fortgesetzt.|  
  
 Im folgenden Codebeispiel wird ein Ereignishandler für das `FillError`-Ereignis `DataAdapter` hinzugefügt. Im `FillError`-Ereigniscode bestimmt das Beispiel, ob die Möglichkeit von Präzisionsverlust besteht, und bietet die Chance, auf die Ausnahme zu reagieren.  
  
```vb  
AddHandler adapter.FillError, New FillErrorEventHandler( _  
  AddressOf FillError)  
  
Dim dataSet As DataSet = New DataSet  
adapter.Fill(dataSet, "ThisTable")  
  
Private Shared Sub FillError(sender As Object, _  
  args As FillErrorEventArgs)  
  If args.Errors.GetType() Is Type.GetType("System.OverflowException") Then  
    ' Code to handle precision loss.  
    ' Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(New Object() _  
      {args.Values(0), args.Values(1), DBNull.Value})  
    ' Set the RowError containing the value for the third column.  
    myRow.RowError = _  
      "OverflowException encountered. Value from data source: " & _  
      args.Values(2)  
    args.Continue = True  
  End If  
End Sub  
```  
  
```csharp  
adapter.FillError += new FillErrorEventHandler(FillError);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "ThisTable");  
  
protected static void FillError(object sender, FillErrorEventArgs args)  
{  
  if (args.Errors.GetType() == typeof(System.OverflowException))  
  {  
    // Code to handle precision loss.  
    //Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(new object[]  
       {args.Values[0], args.Values[1], DBNull.Value});  
    //Set the RowError containing the value for the third column.  
    myRow.RowError =
       "OverflowException Encountered. Value from data source: " +  
       args.Values[2];  
    args.Continue = true;  
  }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [DataAdapters und DataReaders](dataadapters-and-datareaders.md)
- [Handling DataSet Events (Behandeln von DataSet-Ereignissen)](./dataset-datatable-dataview/handling-dataset-events.md)
- [Behandeln von DataTable-Ereignissen](./dataset-datatable-dataview/handling-datatable-events.md)
- [Ereignisse](../../../standard/events/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
