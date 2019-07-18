---
title: Ändern von "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 6e340b9b72735598650d2eefa6e19ab40fffc2e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607413"
---
# <a name="modifying-dataviews"></a>Ändern von "DataViews"
Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden. Die Möglichkeit zum Verwenden der **DataView** zum Ändern von Daten in der zugrunde liegenden Tabelle werden gesteuert, indem eine der drei booleschen Eigenschaften der der **DataView**. Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>. Werden festgelegt, um **"true"** standardmäßig.  
  
 Wenn **AllowNew** ist **"true"**, können Sie die <xref:System.Data.DataView.AddNew%2A> Methode der **DataView** zum Erstellen eines neuen <xref:System.Data.DataRowView>. Beachten Sie, dass eine neue Zeile nicht tatsächlich hinzugefügt, auf die zugrunde liegende <xref:System.Data.DataTable> bis der <xref:System.Data.DataRowView.EndEdit%2A> Methode der **DataRowView** aufgerufen wird. Wenn die <xref:System.Data.DataRowView.CancelEdit%2A> Methode der **DataRowView** wird aufgerufen, wird die neue Zeile verworfen. Beachten Sie, dass Sie nur einen bearbeiten können **DataRowView** zu einem Zeitpunkt. Aufrufen der **AddNew** oder **BeginEdit** Methode der **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** wird implizit aufgerufen werden, auf die ausstehende Zeile. Bei der **EndEdit** wird aufgerufen, die vorgenommenen Änderungen werden auf den zugrunde liegenden **DataTable** und kann später übernommen oder abgelehnt wird, mit der **AcceptChanges** oder  **RejectChanges** Methoden der **DataTable**, **DataSet**, oder **DataRow** Objekt. Wenn **AllowNew** ist **"false"**, eine Ausnahme ausgelöst, wenn der Aufruf der **AddNew** Methode der **DataRowView**.  
  
 Wenn **AllowEdit** ist **"true"**, Sie können den Inhalt einer **DataRow** über der **DataRowView**. Sie können überprüfen, ob Änderungen an der zugrunde liegenden Zeile mithilfe **DataRowView.EndEdit** oder Ablehnen der Änderungen, die mithilfe von **DataRowView.CancelEdit**. Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann. Aufrufen der **AddNew** oder **BeginEdit** Methoden der **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** implizit für aufgerufen die ausstehende Zeile. Bei der **EndEdit** aufgerufen wird, vorgeschlagene Änderungen befinden sich der **aktuelle** Zeilenversion der zugrunde liegenden **DataRow** und kann später übernommen oder abgelehnt wird, verwenden die  **AcceptChanges** oder **RejectChanges** Methoden der **DataTable**, **DataSet**, oder **DataRow** -Objekt. Wenn **AllowEdit** ist **"false"**, eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert im Ändern der **DataView**.  
  
 Wenn ein vorhandenes **DataRowView** bearbeitet wird, Ereignisse des zugrunde liegenden **DataTable** wird weiterhin mit den vorgeschlagenen Änderungen ausgelöst werden. Beachten Sie, dass, wenn Sie aufrufen **EndEdit** oder **CancelEdit** für den zugrunde liegenden **DataRow**, ausstehende Änderungen werden angewendet oder verworfen werden, unabhängig davon, ob  **EndEdit** oder **CancelEdit** aufgerufen wird, auf die **DataRowView**.  
  
 Wenn **AllowDelete** ist **"true"**, können Sie Zeilen löschen der **DataView** mithilfe der **löschen** -Methode der der **"DataView"**  oder **DataRowView** Objekt und die Zeilen werden gelöscht, aus der zugrunde liegenden **DataTable**. Sie können später commit oder Ablehnen der Löschvorgänge, die mithilfe von **AcceptChanges** oder **RejectChanges** bzw. Wenn **AllowDelete** ist **"false"**, eine Ausnahme ausgelöst, wenn Sie aufrufen, die **löschen** Methode der **DataView** oder  **DataRowView**.  
  
 Im folgenden Codebeispiel wird deaktiviert die **DataView** zum Löschen von Zeilen und fügt eine neue Zeile in die zugrunde liegende Tabelle mithilfe der **DataView**.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
