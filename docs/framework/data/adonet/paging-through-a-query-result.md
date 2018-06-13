---
title: Paging durch ein Abfrageergebnis
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 73475f8521b4112929339cc7f1116e36ffebedb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358967"
---
# <a name="paging-through-a-query-result"></a>Paging durch ein Abfrageergebnis
Beim Paging durch ein Abfrageergebnis werden die Ergebnisse einer Abfrage in kleineren Untergruppen von Daten oder Seiten zurückgegeben. Dies ist eine allgemein übliche Vorgehensweise, um einem Benutzer Ergebnisse in kleinen Blöcken anzuzeigen, die sich leicht verwalten lassen.  
  
 Die **"DataAdapter"** bietet die Möglichkeit zum Zurückgeben von nur einer Seite mit Daten, die über Überladungen des der **füllen** Methode. Allerdings dies möglicherweise nicht die beste Wahl für umfangreiche Abfrageergebnisse durchgehen, da Sie zwar die **"DataAdapter"** füllt das Ziel <xref:System.Data.DataTable> oder <xref:System.Data.DataSet> mit nur den angeforderten Datensätzen, die Ressourcen zum Zurückgeben der gesamte Abfrage werden weiterhin verwendet. Geben Sie zusätzliche Kriterien für Ihre Abfrage ein, um eine Seite mit Daten von einer Datenquelle ohne die Ressourcen zurückzugeben, die zum Zurückgeben der gesamten Abfrage erforderlich sind, sodass nur die erforderlichen Zeilen zurückgegeben werden.  
  
 Verwenden der **füllen** Geben Sie die Methode zum Zurückgeben einer Seite der Daten, eine **StartRecord** Parameter, für den ersten Datensatz auf der Seite der Daten, und ein **MaxRecords** -Parameter, für die Anzahl der die Datensätze in die Seite der Daten.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die **füllen** Methode, um die erste Seite eines Abfrageergebnisses zurückzugeben, wobei fünf Datensätze ist die Seitengröße.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Im vorherigen Beispiel der **DataSet** gefüllt wird nur mit fünf Datensätzen, aber die gesamte **Aufträge** Tabelle zurückgegeben. Zum Auffüllen der **DataSet** mit diesen fünf Datensätzen, aber nur fünf Datensätze zurückzugeben, verwenden Sie die TOP und WHERE-Klauseln in der SQL-Anweisung, wie im folgenden Codebeispiel wird.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Wenn Sie die Abfrageergebnisse auf diese Weise durchgehen, müssen Sie den eindeutigen Bezeichner, nach dem die Zeilen geordnet sind, beibehalten, um die eindeutige ID an den Befehl zu übergeben und die nächste Seite mit Datensätzen zurückzugeben (siehe folgendes Codebeispiel).  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Die nächste Seite mit Datensätzen durch die Überladung der zurückzugebenden der **füllen** Methode, die **StartRecord** und **MaxRecords** Parameter, erhöhen Sie den aktuellen Datensatzindex durch die Seitengröße und Ausfüllen der Tabelle. Denken Sie daran, dass der Datenbankserver alle Abfrageergebnisse zurückgibt, selbst wenn nur eine Seite mit Datensätzen hinzugefügt wird die **DataSet**. Im folgenden Codebeispiel wird der Inhalt der Tabellenzeilen gelöscht, bevor sie mit der nächsten Seite mit Daten gefüllt werden. Möglicherweise soll eine bestimmte Anzahl zurückgegebener Zeilen in einem lokalen Cache beibehalten werden, um die Anzahl der Schleifen zum Datenbankserver zu reduzieren.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Geben Sie restriktive Kriterien für die SQL-Anweisung SELECT an, um die nächste Seite mit Datensätzen zurückzugeben, ohne dass der Datenbankserver die gesamte Abfrage zurückgeben muss. Da im vorhergehenden Beispiel der zuletzt zurückgegebene Datensatz beibehalten wurde, können Sie ihn in der WHERE-Klausel verwenden, um – wie im folgenden Codebeispiel gezeigt – einen Ausgangspunkt für die Abfrage anzugeben.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>Siehe auch  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
