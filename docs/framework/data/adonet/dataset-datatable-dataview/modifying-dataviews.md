---
title: "Ändern von \"DataViews\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0a8478e9b21c6c2abdc02677305e468109e7b9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-dataviews"></a>Ändern von "DataViews"
Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden. Die Möglichkeit zum Verwenden der **"DataView"** zum Ändern von Daten in der zugrunde liegenden Tabelle werden gesteuert, indem eine der drei booleschen Eigenschaften der **"DataView"**. Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>. Die Einstellung **"true"** standardmäßig.  
  
 Wenn **AllowNew** ist **"true"**, können Sie die <xref:System.Data.DataView.AddNew%2A> Methode der **"DataView"** zum Erstellen eines neuen <xref:System.Data.DataRowView>. Beachten Sie, dass eine neue Zeile nicht tatsächlich hinzugefügt wird, auf die zugrunde liegende <xref:System.Data.DataTable> bis der <xref:System.Data.DataRowView.EndEdit%2A> Methode der **DataRowView** aufgerufen wird. Wenn die <xref:System.Data.DataRowView.CancelEdit%2A> Methode der **DataRowView** wird aufgerufen, wird die neue Zeile verworfen. Beachten Sie außerdem, dass Sie nur eine bearbeiten können **DataRowView** zu einem Zeitpunkt. Beim Aufrufen der **AddNew** oder **BeginEdit** Methode der **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** wird implizit aufgerufen werden, auf die ausstehende Zeile. Wenn **EndEdit** wird aufgerufen, die vorgenommenen Änderungen werden auf die zugrunde liegende **DataTable** und kann später übernommen oder abgelehnt wird, mit der **AcceptChanges** oder  **RejectChanges** Methoden die **DataTable**, **DataSet**, oder **DataRow** Objekt. Wenn **AllowNew** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie rufen die **AddNew** Methode der **DataRowView**.  
  
 Wenn **AllowEdit** ist **"true"**, können Sie den Inhalt der Ändern einer **DataRow** über die **DataRowView**. Sie können überprüfen, ob Änderungen an der zugrunde liegenden Zeile mit **DataRowView.EndEdit** oder ablehnen die Änderungen mit **DataRowView.CancelEdit**. Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann. Beim Aufrufen der **AddNew** oder **BeginEdit** Methoden die **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** implizit für aufgerufen die ausstehende Zeile. Wenn **EndEdit** aufgerufen wird, vorgeschlagene Änderungen befinden sich der **aktuelle** Zeilenversion der zugrunde liegenden **DataRow** und kann später übernommen oder abgelehnt wird, verwenden die  **AcceptChanges** oder **RejectChanges** Methoden die **DataTable**, **DataSet**, oder **DataRow** -Objekt. Wenn **AllowEdit** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie versuchen, einen Wert im Ändern der **"DataView"**.  
  
 Wenn eine vorhandene **DataRowView** bearbeitet wird, Ereignisse der zugrunde liegenden **DataTable** weiterhin mit den vorgeschlagenen Änderungen ausgelöst werden soll. Beachten Sie, dass beim Aufrufen **EndEdit** oder **CancelEdit** für den zugrunde liegenden **DataRow**, ausstehende Änderungen angewendet oder abgebrochen wird, unabhängig davon, ob  **EndEdit** oder **CancelEdit** aufgerufen wird, auf die **DataRowView**.  
  
 Wenn **AllowDelete** ist **"true"**, können Sie Zeilen aus Löschen der **"DataView"** mithilfe der **löschen** Methode der **"DataView"**  oder **DataRowView** Objekt und die Zeilen werden gelöscht, aus der zugrunde liegenden **DataTable**. Später bestätigen oder Ablehnen der Löschvorgänge über können **AcceptChanges** oder **RejectChanges** bzw.. Wenn **AllowDelete** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie rufen die **löschen** Methode der **"DataView"** oder  **DataRowView**.  
  
 Deaktiviert im folgenden Codebeispiel wird die Verwendung der **"DataView"** zum Löschen von Zeilen und fügt eine neue Zeile der zugrunde liegenden Tabelle mithilfe der **"DataView"**.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
