---
title: Ändern von "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 0b2bfd1b0490572e78c8ce365491a8d48db87684
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204570"
---
# <a name="modifying-dataviews"></a>Ändern von "DataViews"
Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden. Die Möglichkeit, die **DataView** zum Ändern von Daten in der zugrunde liegenden Tabelle zu verwenden, wird gesteuert, indem eine der drei booleschen Eigenschaften der **DataView**-Eigenschaft festgelegt wird. Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>. Sie werden standardmäßig auf **true** festgelegt.  
  
 Wenn **AllowNew** den Wert **true**hat, können Sie <xref:System.Data.DataView.AddNew%2A> die-Methode der **DataView** verwenden, um <xref:System.Data.DataRowView>eine neue zu erstellen. Beachten Sie, dass dem zugrunde liegenden <xref:System.Data.DataTable> erst dann eine neue Zeile hinzugefügt wird, wenn die <xref:System.Data.DataRowView.EndEdit%2A> -Methode der **DataRowView** aufgerufen wird. Wenn die <xref:System.Data.DataRowView.CancelEdit%2A> -Methode der **DataRowView** aufgerufen wird, wird die neue Zeile verworfen. Beachten Sie auch, dass Sie jeweils nur eine **DataRowView** bearbeiten können. Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen. Wenn **EndEdit** aufgerufen wird, werden die Änderungen auf die zugrunde liegende **Daten** Tabelle angewendet und können später mithilfe der Methoden " **akzeptchanges** " oder " **RejectChanges** " der **Daten**Tabelle, des **DataSets** **oder des DataRow** -Objekt. Wenn **AllowNew** **false**ist, wird eine Ausnahme ausgelöst, wenn Sie die **AddNew** -Methode der **DataRowView**aufrufen.  
  
 Wenn " **Zuweisung** " den Wert " **true**" hat, können Sie den Inhalt einer **DataRow** über die " **DataRowView**" ändern. Sie können Änderungen an der zugrunde liegenden Zeile mithilfe von " **DataRowView. EndEdit** " bestätigen oder die Änderungen mithilfe von " **DataRowView. CancelEdit**" ablehnen. Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann. Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen. Wenn **EndEdit** aufgerufen wird, werden vorgeschlagene Änderungen in der **aktuellen** Zeilen Version der zugrunde liegenden **DataRow** abgelegt und können später mithilfe der Methoden " **akzeptchanges** " oder " **RejectChanges** " des  **Daten**Tabelle, **DataSet**oder **DataRow** -Objekt. Wenn " **zugwedit** " den Wert " **false**" hat, wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert in der **DataView**zu ändern.  
  
 Wenn eine vorhandene **DataRowView** bearbeitet wird, werden Ereignisse der zugrunde liegenden **Daten** Tabelle weiterhin mit den vorgeschlagenen Änderungen ausgelöst. Beachten Sie, dass beim Aufrufen von **EndEdit** oder **CancelEdit** für die zugrunde liegende **DataRow**ausstehende Änderungen angewendet oder abgebrochen werden, unabhängig davon, ob **EndEdit** oder **CancelEdit** für die **DataRowView**aufgerufen wird.  
  
 Wenn **AllowDelete** den Wert **true**hat, können Sie Zeilen aus der **DataView** löschen, indem Sie die **Delete** -Methode des **DataView** -Objekts oder des **DataRowView** -Objekts verwenden, und die Zeilen werden aus der zugrunde liegenden **Daten**Tabelle gelöscht. Sie können später commit oder Ablehnen der Löschvorgänge, die mithilfe von **AcceptChanges** oder **RejectChanges** bzw. Wenn **AllowDelete** den Wert **false**hat, wird eine Ausnahme ausgelöst, wenn Sie die **Delete** -Methode von **DataView** oder **DataRowView**aufrufen.  
  
 Im folgenden Codebeispiel wird die Verwendung von **DataView** zum Löschen von Zeilen und das Hinzufügen einer neuen Zeile zur zugrunde liegenden Tabelle mithilfe von **DataView**deaktiviert.  
  
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
- [DataViews](dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
