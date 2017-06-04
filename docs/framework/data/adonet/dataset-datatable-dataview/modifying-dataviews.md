---
title: "Bearbeiten von &#39;DataViews&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Bearbeiten von &#39;DataViews&#39;
Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden.  Die Möglichkeit, mit **DataView** Datenzeilen in der zugrunde liegenden Tabelle zu ändern, wird durch Festlegen einer der drei booleschen Eigenschaften der **DataView** gesteuert.  Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>.  Sie sind in der Standardeinstellung auf **true** festgelegt.  
  
 Wenn **AllowNew** auf **true** festgelegt ist, kann die <xref:System.Data.DataView.AddNew%2A>\-Methode der **DataView** zum Erstellen einer neuen <xref:System.Data.DataRowView> verwendet werden.  Beachten Sie, dass die neue Zeile der zugrunde liegenden <xref:System.Data.DataTable> erst hinzugefügt wird, wenn die <xref:System.Data.DataRowView.EndEdit%2A>\-Methode der **DataRowView** aufgerufen wird.  Wenn die <xref:System.Data.DataRowView.CancelEdit%2A>\-Methode der **DataRowView** aufgerufen wird, wird die neue Zeile verworfen.  Beachten Sie auch, dass Sie jeweils nur eine **DataRowView** bearbeiten können.  Wenn Sie die **AddNew**\-Methode oder die **BeginEdit**\-Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen.  Wenn **EndEdit** aufgerufen wird, werden die Änderungen auf die zugrunde liegende **DataTable** angewendet und können später mithilfe der **AcceptChanges**\-Methode oder der **RejectChanges**\-Methode der Objekte **DataTable**, **DataSet** oder **DataRow** übernommen oder abgelehnt werden.  Wenn **AllowNew** auf **false** festgelegt ist, wird beim Aufrufen der **AddNew**\-Methode der **DataRowView** eine Ausnahme ausgelöst.  
  
 Wenn **AllowEdit** auf **true** festgelegt ist, können Sie mithilfe der **DataRowView** den Inhalt einer **DataRow** ändern.  Mit **DataRowView.EndEdit** können Sie die Änderungen an der zugrunde liegenden Zeile bestätigen oder sie mit **DataRowView.CancelEdit** ablehnen.  Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann.  Wenn Sie die **AddNew**\-Methode oder die **BeginEdit**\-Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen.  Wenn **EndEdit** aufgerufen wird, werden die vorgeschlagenen Änderungen in der **Current**\-Zeilenversion der zugrunde liegenden **DataRow** platziert und können später mithilfe der **AcceptChanges**\-Methode oder der **RejectChanges**\-Methode der Objekte **DataTable**, **DataSet** oder **DataRow** übernommen oder abgelehnt werden.  Wenn **AllowEdit** auf **false** festgelegt ist, wird bei dem Versuch, einen Wert in der **DataView** zu ändern, eine Ausnahme ausgelöst.  
  
 Wenn eine vorhandene **DataRowView** bearbeitet wird, werden Ereignisse der zugrunde liegenden **DataTable** weiterhin mit den vorgeschlagenen Änderungen ausgelöst.  Wenn Sie **EndEdit** oder **CancelEdit** für die zugrunde liegende **DataRow** aufrufen, werden ausstehende Änderungen angewendet oder verworfen, unabhängig davon, ob **EndEdit** oder **CancelEdit** für **DataRowView** aufgerufen wird.  
  
 Wenn **AllowDelete** auf **true** festgelegt ist, können Sie mit der **Delete**\-Methode des **DataView**\-Objekts oder des **DataRowView**\-Objekts Zeilen aus der **DataView** löschen. Die Zeilen werden aus der zugrundeliegenden **DataTable** gelöscht.  	Sie können die Löschvorgänge später mit **AcceptChanges** oder **RejectChanges** übernehmen oder ablehnen.  Wenn **AllowDelete** auf **false** festgelegt ist, wird beim Aufrufen der **Delete**\-Methode des **DataView**\-Objekts oder des **DataRowView**\-Objekts eine Ausnahme ausgelöst.  
  
 Im folgenden Codebeispiel wird **DataView** für das Löschen von Zeilen deaktiviert und mit **DataView** der zugrunde liegenden Tabelle eine neue Zeile hinzugefügt.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## Siehe auch  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)