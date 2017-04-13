---
title: "Die &#39;Load&#39;-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Die &#39;Load&#39;-Methode
Mithilfe der <xref:System.Data.DataTable.Load%2A>\-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden.  Dies ist eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter, einen **DataReader**, akzeptiert.  In dieser Form lädt sie einfach die **DataTable** mit Zeilen.  Optional können Sie den **LoadOption**\-Parameter angeben, um zu steuern, wie der **DataTable** die Daten hinzugefügt werden.  
  
 Der **LoadOption**\-Parameter ist besonders in den Fällen nützlich, in denen die **DataTable** bereits Zeilen mit Daten enthält, weil durch den Parameter beschrieben wird, wie die eingehenden Daten aus der Datenquelle mit den bereits in der Tabelle vorhandenen Daten kombiniert werden.  Beispielsweise wird durch den Standardwert **PreserveCurrentValues** angegeben, dass dann, wenn eine Zeile als **Added** in der **DataTable** markiert ist, der **Original**\-Wert jeder Spalte auf den Inhalt der entsprechenden Zeile aus der Datenquelle festgelegt wird.  Der **Current**\-Wert behält die Werte bei, die ihm beim Hinzufügen der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf **Changed** festgelegt.  
  
 Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>\-Enumerationswerte.  
  
|Der LoadOption\-Wert|Beschreibung|  
|--------------------------|------------------|  
|**OverwriteRow**|Wenn hinzukommende Zeilen denselben **PrimaryKey**\-Wert wie eine bereits in der **DataTable** vorhandene Zeile aufweisen, werden der **Original**\-Wert und der **Current**\-Wert jeder Spalte durch die Werte in der hinzukommenden Zeile ersetzt, und die **RowState**\-Eigenschaft wird auf **Unchanged** festgelegt.<br /><br /> Zeilen aus einer Datenquelle, die in der **DataTable** noch nicht vorhanden sind, werden mit dem **RowState**\-Wert **Unchanged** hinzugefügt.<br /><br /> Mit dieser Option wird der Inhalt der **DataTable** aktualisiert, sodass er mit dem Inhalt der Datenquelle übereinstimmt.|  
|**PreserveCurrentValues \(Standard\)**|Wenn hinzukommende Zeilen denselben **PrimaryKey**\-Wert wie eine bereits in der **DataTable** vorhandene Zeile aufweisen, wird der **Original**\-Wert auf den Inhalt der hinzukommenden Zeile festgelegt, und der **Current**\-Wert wird nicht geändert.<br /><br /> Wenn der **RowState** den Wert **Added** oder den Wert **Modified** aufweist, wird er auf **Modified** festgelegt.<br /><br /> Wenn der **RowState** den Wert **Deleted** besitzt, bleibt er **Deleted**.<br /><br /> Zeilen aus einer Datenquelle, die in der **DataTable** noch nicht vorhanden sind, werden hinzugefügt, und der **RowState**\-Wert wird auf **Unchanged** festgelegt.|  
|**UpdateCurrentValues**|Wenn hinzukommende Zeilen denselben **PrimaryKey**\-Wert wie die bereits in der **DataTable** vorhandene Zeile aufweisen, wird der **Current**\-Wert in den **Original**\-Wert kopiert, und der **Current**\-Wert wird anschließend auf den Inhalt der hinzukommenden Zeile festgelegt.<br /><br /> Wenn der **RowState** in der **DataTable** den Wert **Added** aufwies, wird für den **RowState** der Wert **Added** beibehalten.  Für Zeilen mit der Markierung **Modified** oder **Deleted** lautet der **RowState** **Modified**.<br /><br /> Zeilen aus einer Datenquelle, die in der **DataTable** noch nicht vorhanden sind, werden hinzugefügt, und der **RowState**\-Wert wird auf **Added** festgelegt.|  
  
 Im folgenden Beispiel wird mit der **Load**\-Methode eine Geburtstagsliste der Mitarbeiter in der **Northwind**\-Datenbank angezeigt.  
  
 \[Visual Basic\]  
  
```  
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
  
## Siehe auch  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)