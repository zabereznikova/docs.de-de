---
title: Paging durch ein Abfrageergebnis
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 065b509d8385ee37b2a86587f520b5fd3207ceff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186951"
---
# <a name="paging-through-a-query-result"></a>Paging durch ein Abfrageergebnis

Beim Paging durch ein Abfrageergebnis werden die Ergebnisse einer Abfrage in kleineren Untergruppen von Daten oder Seiten zurückgegeben. Dies ist eine allgemein übliche Vorgehensweise, um einem Benutzer Ergebnisse in kleinen Blöcken anzuzeigen, die sich leicht verwalten lassen.  
  
 Der **DataAdapter** bietet eine Möglichkeit, nur eine Datenseite über über Ladungen der **Fill** -Methode zurückzugeben. Dies ist jedoch möglicherweise nicht die beste Wahl für das Paging durch große Abfrageergebnisse, denn obwohl der **DataAdapter** das Ziel <xref:System.Data.DataTable> oder <xref:System.Data.DataSet> nur die angeforderten Datensätze füllt, werden die Ressourcen, die die gesamte Abfrage zurückgeben, weiterhin verwendet. Geben Sie zusätzliche Kriterien für Ihre Abfrage ein, um eine Seite mit Daten von einer Datenquelle ohne die Ressourcen zurückzugeben, die zum Zurückgeben der gesamten Abfrage erforderlich sind, sodass nur die erforderlichen Zeilen zurückgegeben werden.  
  
 Um die **Fill** -Methode zum Zurückgeben einer Datenseite zu verwenden, geben Sie für den ersten Datensatz auf der Datenseite einen **startRecord** -Parameter und einen **maxRecords** -Parameter für die Anzahl der Datensätze auf der Datenseite an.  
  
 Im folgenden Codebeispiel wird gezeigt, wie die **Fill** -Methode verwendet wird, um die erste Seite eines Abfrage Ergebnisses zurückzugeben, bei der die Seitengröße fünf Datensätze ist.  
  
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
  
 Im vorherigen Beispiel ist das **DataSet** nur mit fünf Datensätzen gefüllt, aber die gesamte **Orders** -Tabelle wird zurückgegeben. Um das **DataSet** mit denselben fünf Datensätzen zu füllen, aber nur fünf Datensätze zurückgeben, verwenden Sie die Top-Klausel und die WHERE-Klausel in der SQL-Anweisung, wie im folgenden Codebeispiel gezeigt.  
  
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
  
 Um die nächste Seite mit Datensätzen zurückzugeben, indem Sie die Überladung der **Fill** -Methode verwenden, die die Parameter **startRecord** und **maxRecords** annimmt, erhöhen Sie den aktuellen Daten Satz Index um die Seitengröße, und füllen Sie die Tabelle aus. Beachten Sie, dass der Datenbankserver die gesamten Abfrageergebnisse zurückgibt, obwohl nur eine Seite mit Datensätzen dem **DataSet**hinzugefügt wird. Im folgenden Codebeispiel wird der Inhalt der Tabellenzeilen gelöscht, bevor sie mit der nächsten Seite mit Daten gefüllt werden. Möglicherweise soll eine bestimmte Anzahl zurückgegebener Zeilen in einem lokalen Cache beibehalten werden, um die Anzahl der Schleifen zum Datenbankserver zu reduzieren.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
