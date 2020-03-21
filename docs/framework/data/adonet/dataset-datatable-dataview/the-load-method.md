---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150726"
---
# <a name="the-load-method"></a>Load-Methode
Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden. Dies ist eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter akzeptiert, einen **DataReader**. In diesem Formular wird die **DataTable** einfach mit Zeilen geladen. Optional können Sie den **LoadOption-Parameter** angeben, um zu steuern, wie Daten der **DataTable**hinzugefügt werden.  
  
 Der **LoadOption-Parameter** ist besonders nützlich in Fällen, in denen die **DataTable** bereits Datenzeilen enthält, da er beschreibt, wie eingehende Daten aus der Datenquelle mit den daten kombiniert werden, die bereits in der Tabelle enthalten sind. **PreserveCurrentValues** (Standardeinstellung) gibt beispielsweise an, dass in Fällen, in denen eine Zeile in der **DataTable**als **hinzugefügt** markiert ist, der **Ursprüngliche** Wert oder jede Spalte auf den Inhalt der übereinstimmenden Zeile aus der Datenquelle festgelegt ist. Der **aktuelle** Wert behält die Werte bei, die beim Addieren der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf **Geändert**festgelegt.  
  
 Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.  
  
|Der LoadOption-Wert|Beschreibung|  
|----------------------|-----------------|  
|**OverwriteRow**|Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie eine Zeile haben, die sich bereits in der **DataTable**befindet, werden die **ursprünglichen** und **aktuellen** Werte jeder Spalte durch die Werte in der eingehenden Zeile ersetzt, und die **RowState-Eigenschaft** wird auf **Unchanged**festgelegt.<br /><br /> Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden mit dem **RowState-Wert** **Unchanged**hinzugefügt.<br /><br /> Diese Option aktualisiert den Inhalt der **DataTable,** sodass sie mit dem Inhalt der Datenquelle übereinstimmt.|  
|**PreserveCurrentValues (Standard)**|Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie eine Zeile haben, die sich bereits in der **DataTable**befindet, wird der **Ursprüngliche** Wert auf den Inhalt der eingehenden Zeile festgelegt, und der **aktuelle** Wert wird nicht geändert.<br /><br /> Wenn **RowState** **hinzugefügt** oder **geändert**wird, wird er auf **Modified**festgelegt.<br /><br /> Wenn der **RowState** **gelöscht**wurde, bleibt er **gelöscht**.<br /><br /> Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden hinzugefügt, und **RowState** wird auf **Unchanged**festgelegt.|  
|**UpdateCurrentValues**|Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie die Zeile haben, die sich bereits in der **DataTable**befindet, wird der **aktuelle** Wert in den **Ursprünglichen** Wert kopiert, und der **aktuelle** Wert wird dann auf den Inhalt der eingehenden Zeile festgelegt.<br /><br /> Wenn der **RowState** in der **DataTable** **hinzugefügt**wurde, bleibt der **RowState** **hinzugefügt**. Für Zeilen, die als **geändert** oder **gelöscht**markiert sind, ist der **RowState** **Modified**.<br /><br /> Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden hinzugefügt, und **RowState** ist auf **Added**festgelegt.|  
  
 Im folgenden Beispiel wird die **Load-Methode** verwendet, um eine Liste der Geburtstage für die Mitarbeiter in der **Northwind-Datenbank** anzuzeigen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Bearbeiten von Daten in einer "DataTable"](manipulating-data-in-a-datatable.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
