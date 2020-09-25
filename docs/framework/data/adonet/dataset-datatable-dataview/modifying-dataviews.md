---
title: Ändern von "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 8e3a3f92fe8ecc94a041fbcb1540bae18a41dbef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203682"
---
# <a name="modifying-dataviews"></a>Ändern von "DataViews"

Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden. Die Möglichkeit, die **DataView** zum Ändern von Daten in der zugrunde liegenden Tabelle zu verwenden, wird gesteuert, indem eine der drei booleschen Eigenschaften der **DataView**-Eigenschaft festgelegt wird. Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>. Sie werden standardmäßig auf **true** festgelegt.  
  
 Wenn **AllowNew** den Wert **true**hat, können Sie die- <xref:System.Data.DataView.AddNew%2A> Methode der **DataView** verwenden, um eine neue zu erstellen <xref:System.Data.DataRowView> . Beachten Sie, dass dem zugrunde liegenden erst dann eine neue Zeile hinzugefügt wird, <xref:System.Data.DataTable> Wenn die- <xref:System.Data.DataRowView.EndEdit%2A> Methode der **DataRowView** aufgerufen wird. Wenn die- <xref:System.Data.DataRowView.CancelEdit%2A> Methode der **DataRowView** aufgerufen wird, wird die neue Zeile verworfen. Beachten Sie auch, dass Sie jeweils nur eine **DataRowView** bearbeiten können. Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen. Wenn **EndEdit** aufgerufen wird, werden die Änderungen auf die zugrunde liegende **Daten** Tabelle angewendet und können später mithilfe der Methoden accept- **Changes** oder **RejectChanges** des **Datable**-, **DataSet**-oder **DataRow** -Objekts ausgeführt oder abgelehnt werden. Wenn **AllowNew** **false**ist, wird eine Ausnahme ausgelöst, wenn Sie die **AddNew** -Methode der **DataRowView**aufrufen.  
  
 Wenn " **Zuweisung** " den Wert " **true**" hat, können Sie den Inhalt einer **DataRow** über die " **DataRowView**" ändern. Sie können Änderungen an der zugrunde liegenden Zeile mithilfe von " **DataRowView. EndEdit** " bestätigen oder die Änderungen mithilfe von " **DataRowView. CancelEdit**" ablehnen. Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann. Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen. Wenn **EndEdit** aufgerufen wird, werden vorgeschlagene Änderungen in der **aktuellen** Zeilen Version der zugrunde liegenden **DataRow** abgelegt und können später mithilfe der Methoden " **akzeptchanges** " oder " **RejectChanges** " des **Datable**-, **DataSet**-oder **DataRow** -Objekts ausgeführt oder abgelehnt werden. Wenn " **zugwedit** " den Wert " **false**" hat, wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert in der **DataView**zu ändern.  
  
 Wenn eine vorhandene **DataRowView** bearbeitet wird, werden Ereignisse der zugrunde liegenden **Daten** Tabelle weiterhin mit den vorgeschlagenen Änderungen ausgelöst. Beachten Sie, dass beim Aufrufen von **EndEdit** oder **CancelEdit** für die zugrunde liegende **DataRow**ausstehende Änderungen angewendet oder abgebrochen werden, unabhängig davon, ob **EndEdit** oder **CancelEdit** für die **DataRowView**aufgerufen wird.  
  
 Wenn **AllowDelete** den Wert **true**hat, können Sie Zeilen aus der **DataView** löschen, indem Sie die **Delete** -Methode des **DataView** -Objekts oder des **DataRowView** -Objekts verwenden, und die Zeilen werden aus der zugrunde liegenden **Daten**Tabelle gelöscht. Sie können die Löschvorgänge später mithilfe von " **akzeptchanges** " oder " **RejectChanges** " übertragen oder ablehnen. Wenn **AllowDelete** den Wert **false**hat, wird eine Ausnahme ausgelöst, wenn Sie die **Delete** -Methode von **DataView** oder **DataRowView**aufrufen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- ["DataViews"](dataviews.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
