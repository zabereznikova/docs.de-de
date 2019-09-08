---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: da0695aff9447355b1fc44a033c1b4a1cc224435
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785880"
---
# <a name="the-load-method"></a>Load-Methode
Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden. Dabei handelt es sich um eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter ( **DataReader**) akzeptiert. In diesem Formular wird die **Daten** Tabelle einfach mit Zeilen geladen. Optional können Sie den **LoadOption** -Parameter angeben, um zu steuern, wie **Daten der Daten**Tabelle hinzugefügt werden.  
  
 Der **LoadOption** -Parameter ist besonders nützlich in Fällen, in denen die Datentabelle bereits Daten Zeilen enthält, da Sie beschreibt, **wie die Eingeh** enden Daten aus der Datenquelle mit den bereits in der Tabelle enthaltenen Daten kombiniert werden. Beispielsweise gibt " **Konservierungs-ecurrentvalues** " (Standardwert) an, dass in Fällen, in denen eine Zeile in der Datentabelle als **hinzugefügt** gekennzeichnet **ist, der** **ursprüngliche** Wert oder jede Spalte auf den Inhalt der übereinstimmenden Zeile aus der Datenquelle festgelegt wird. Der **aktuelle** Wert behält die Werte bei, die beim Hinzufügen der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf " **geändert**" festgelegt.  
  
 Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.  
  
|Der LoadOption-Wert|Beschreibung|  
|----------------------|-----------------|  
|**OverwriteRow**|Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der **Daten**Tabelle geltende Zeile aufweisen, werden die **ursprünglichen** und **aktuellen** Werte jeder Spalte durch die Werte in der eingehenden Zeile ersetzt, und die **RowState** -Eigenschaft wird auf festgelegt. **Unverändert**.<br /><br /> Zeilen aus der Datenquelle, die nicht bereits in der Datentabelle **vorhanden sind, werden mit dem** **RowState** -Wert **unverändert**hinzugefügt.<br /><br /> Mit dieser Option wird der Inhalt der Datentabelle aktualisiert **, sodass Sie** mit dem Inhalt der Datenquelle übereinstimmt.|  
|**Konserviecurrentvalues (Standard)**|Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **ursprüngliche** Wert auf den Inhalt der eingehenden Zeile festgelegt, und der **aktuelle** Wert wird nicht geändert.<br /><br /> Wenn der **RowState** **hinzugefügt** oder **geändert**wird, wird er auf **modified**festgelegt.<br /><br /> Wenn der **RowState** **gelöscht**wurde, bleibt er **gelöscht**.<br /><br /> Zeilen aus der Datenquelle **, die nicht** bereits in der Datentabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf " **unverändert**" festgelegt.|  
|**UpdateCurrentValues**|Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie die bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **aktuelle** Wert in den **ursprünglichen** Wert kopiert, und der **aktuelle** Wert wird dann auf den Inhalt der eingehenden Zeile festgelegt.<br /><br /> Wenn der **RowState** in der **Daten** Tabelle **hinzugefügt**wurde, wird der **RowState** weiterhin **hinzugefügt**. Für Zeilen, die als **geändert** oder **gelöscht**markiert sind, wird der **RowState** **geändert**.<br /><br /> Zeilen aus der Datenquelle **, die nicht** bereits in der Datentabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf **Added**festgelegt.|  
  
 Im folgenden Beispiel wird die **Load** -Methode verwendet, um eine Liste der Geburtstage für die Mitarbeiter in der **Northwind** -Datenbank anzuzeigen.  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch

- [Bearbeiten von Daten in einer DataTable](manipulating-data-in-a-datatable.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
