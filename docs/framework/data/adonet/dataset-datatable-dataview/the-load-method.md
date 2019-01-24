---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 06666e069f20bc06f303c4e829d1c69c185a8a84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602480"
---
# <a name="the-load-method"></a>Load-Methode
Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden. Dies ist eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter akzeptiert eine **DataReader**. Bei dieser Form lädt sie einfach die **DataTable** mit Zeilen. Optional können Sie angeben der **LoadOption** Parameter, um zu steuern, wie Daten hinzugefügt werden die **DataTable**.  
  
 Die **LoadOption** Parameter ist besonders nützlich in Fällen, in denen die **DataTable** bereits Datenzeilen enthält, da es wird beschrieben, wie die eingehenden Daten aus der Datenquelle wird mit den Daten kombiniert werden bereits in der Tabelle. Z. B. **PreserveCurrentValues** (Standard) gibt an, dass in Fällen, in dem eine Zeile als markiert ist **Added** in die **DataTable**, **ursprünglichen** Wert oder jede Spalte ist auf den Inhalt der entsprechenden Zeile aus der Datenquelle festgelegt. Die **aktuelle** -Wert behält die Werte zugewiesen, wenn die Zeile hinzugefügt wurde, und die **RowState** der Zeile festgelegt **Changed**.  
  
 Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.  
  
|Der LoadOption-Wert|Beschreibung|  
|----------------------|-----------------|  
|**OverwriteRow**|Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert als eine Zeile, die bereits in der **DataTable**, **ursprünglichen** und **aktuelle** Werte der einzelnen mit den Werten in der eingehenden Zeile, Spalte ersetzt werden und die **RowState** -Eigenschaftensatz auf **Unchanged**.<br /><br /> Zeilen aus der Datenquelle, die in noch nicht vorhanden sind die **DataTable** werden hinzugefügt, mit einer **RowState** Wert **Unchanged**.<br /><br /> Diese Option wirksam aktualisiert den Inhalt der **DataTable** so, dass sie den Inhalt der Datenquelle übereinstimmt.|  
|**PreserveCurrentValues (Standard)**|Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert als eine Zeile, die bereits in der **DataTable**, **ursprünglichen** Wert wird festgelegt, auf den Inhalt der hinzukommenden Zeile, und die **Aktuelle** Wert wird nicht geändert.<br /><br /> Wenn die **RowState** ist **Added** oder **"geändert"**, festgelegt ist **"geändert"**.<br /><br /> Wenn die **RowState** wurde **gelöschte**, bleibt er **gelöschte**.<br /><br /> Zeilen aus der Datenquelle, die nicht bereits vorhanden sind in der **DataTable** hinzugefügt werden, und die **RowState** nastaven NA hodnotu **Unchanged**.|  
|**UpdateCurrentValues**|Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert wie die Zeile, die bereits in der **DataTable**, **aktuelle** Wert wird in kopiert die **ursprünglichen**Wert und die **aktuelle** Wert wird auf den Inhalt der hinzukommenden Zeile festgelegt.<br /><br /> Wenn die **RowState** in die **DataTable** wurde **Added**, **RowState** bleibt **Added**. Für Zeilen mit der Markierung **"geändert"** oder **gelöschte**, **RowState** ist **"geändert"**.<br /><br /> Zeilen aus der Datenquelle, die in noch nicht vorhanden sind die **DataTable** hinzugefügt werden, und die **RowState** nastaven NA hodnotu **Added**.|  
  
 Das folgende Beispiel verwendet die **Load** Methode, um eine Liste der Geburtstage für Mitarbeiter im Anzeigen der **Northwind** Datenbank.  
  
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
- [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
