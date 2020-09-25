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
# <a name="modifying-dataviews"></a><span data-ttu-id="934e0-102">Ändern von "DataViews"</span><span class="sxs-lookup"><span data-stu-id="934e0-102">Modifying DataViews</span></span>

<span data-ttu-id="934e0-103">Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="934e0-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="934e0-104">Die Möglichkeit, die **DataView** zum Ändern von Daten in der zugrunde liegenden Tabelle zu verwenden, wird gesteuert, indem eine der drei booleschen Eigenschaften der **DataView**-Eigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="934e0-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="934e0-105">Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="934e0-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="934e0-106">Sie werden standardmäßig auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="934e0-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="934e0-107">Wenn **AllowNew** den Wert **true**hat, können Sie die- <xref:System.Data.DataView.AddNew%2A> Methode der **DataView** verwenden, um eine neue zu erstellen <xref:System.Data.DataRowView> .</span><span class="sxs-lookup"><span data-stu-id="934e0-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="934e0-108">Beachten Sie, dass dem zugrunde liegenden erst dann eine neue Zeile hinzugefügt wird, <xref:System.Data.DataTable> Wenn die- <xref:System.Data.DataRowView.EndEdit%2A> Methode der **DataRowView** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="934e0-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="934e0-109">Wenn die- <xref:System.Data.DataRowView.CancelEdit%2A> Methode der **DataRowView** aufgerufen wird, wird die neue Zeile verworfen.</span><span class="sxs-lookup"><span data-stu-id="934e0-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="934e0-110">Beachten Sie auch, dass Sie jeweils nur eine **DataRowView** bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="934e0-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="934e0-111">Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="934e0-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="934e0-112">Wenn **EndEdit** aufgerufen wird, werden die Änderungen auf die zugrunde liegende **Daten** Tabelle angewendet und können später mithilfe der Methoden accept- **Changes** oder **RejectChanges** des **Datable**-, **DataSet**-oder **DataRow** -Objekts ausgeführt oder abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="934e0-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="934e0-113">Wenn **AllowNew** **false**ist, wird eine Ausnahme ausgelöst, wenn Sie die **AddNew** -Methode der **DataRowView**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="934e0-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="934e0-114">Wenn " **Zuweisung** " den Wert " **true**" hat, können Sie den Inhalt einer **DataRow** über die " **DataRowView**" ändern.</span><span class="sxs-lookup"><span data-stu-id="934e0-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="934e0-115">Sie können Änderungen an der zugrunde liegenden Zeile mithilfe von " **DataRowView. EndEdit** " bestätigen oder die Änderungen mithilfe von " **DataRowView. CancelEdit**" ablehnen.</span><span class="sxs-lookup"><span data-stu-id="934e0-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="934e0-116">Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="934e0-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="934e0-117">Wenn Sie die **AddNew** -Methode oder die **BeginEdit** -Methode der **DataRowView** aufrufen, während eine ausstehende Zeile vorhanden ist, wird **EndEdit** implizit für die ausstehende Zeile aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="934e0-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="934e0-118">Wenn **EndEdit** aufgerufen wird, werden vorgeschlagene Änderungen in der **aktuellen** Zeilen Version der zugrunde liegenden **DataRow** abgelegt und können später mithilfe der Methoden " **akzeptchanges** " oder " **RejectChanges** " des **Datable**-, **DataSet**-oder **DataRow** -Objekts ausgeführt oder abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="934e0-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="934e0-119">Wenn " **zugwedit** " den Wert " **false**" hat, wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert in der **DataView**zu ändern.</span><span class="sxs-lookup"><span data-stu-id="934e0-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="934e0-120">Wenn eine vorhandene **DataRowView** bearbeitet wird, werden Ereignisse der zugrunde liegenden **Daten** Tabelle weiterhin mit den vorgeschlagenen Änderungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="934e0-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="934e0-121">Beachten Sie, dass beim Aufrufen von **EndEdit** oder **CancelEdit** für die zugrunde liegende **DataRow**ausstehende Änderungen angewendet oder abgebrochen werden, unabhängig davon, ob **EndEdit** oder **CancelEdit** für die **DataRowView**aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="934e0-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="934e0-122">Wenn **AllowDelete** den Wert **true**hat, können Sie Zeilen aus der **DataView** löschen, indem Sie die **Delete** -Methode des **DataView** -Objekts oder des **DataRowView** -Objekts verwenden, und die Zeilen werden aus der zugrunde liegenden **Daten**Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="934e0-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="934e0-123">Sie können die Löschvorgänge später mithilfe von " **akzeptchanges** " oder " **RejectChanges** " übertragen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="934e0-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="934e0-124">Wenn **AllowDelete** den Wert **false**hat, wird eine Ausnahme ausgelöst, wenn Sie die **Delete** -Methode von **DataView** oder **DataRowView**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="934e0-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="934e0-125">Im folgenden Codebeispiel wird die Verwendung von **DataView** zum Löschen von Zeilen und das Hinzufügen einer neuen Zeile zur zugrunde liegenden Tabelle mithilfe von **DataView**deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="934e0-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="934e0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="934e0-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="934e0-127">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="934e0-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="934e0-128">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="934e0-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
