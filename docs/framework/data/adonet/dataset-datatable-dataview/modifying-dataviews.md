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
# <a name="modifying-dataviews"></a><span data-ttu-id="b57c7-102">Ändern von "DataViews"</span><span class="sxs-lookup"><span data-stu-id="b57c7-102">Modifying DataViews</span></span>
<span data-ttu-id="b57c7-103">Mit <xref:System.Data.DataView> können Datenzeilen in der zugrunde liegenden Tabelle hinzugefügt, gelöscht oder bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b57c7-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="b57c7-104">Die Möglichkeit zum Verwenden der **"DataView"** zum Ändern von Daten in der zugrunde liegenden Tabelle werden gesteuert, indem eine der drei booleschen Eigenschaften der **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="b57c7-105">Bei diesen Eigenschaften handelt es sich um <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> und <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="b57c7-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="b57c7-106">Die Einstellung **"true"** standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="b57c7-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="b57c7-107">Wenn **AllowNew** ist **"true"**, können Sie die <xref:System.Data.DataView.AddNew%2A> Methode der **"DataView"** zum Erstellen eines neuen <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="b57c7-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="b57c7-108">Beachten Sie, dass eine neue Zeile nicht tatsächlich hinzugefügt wird, auf die zugrunde liegende <xref:System.Data.DataTable> bis der <xref:System.Data.DataRowView.EndEdit%2A> Methode der **DataRowView** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b57c7-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="b57c7-109">Wenn die <xref:System.Data.DataRowView.CancelEdit%2A> Methode der **DataRowView** wird aufgerufen, wird die neue Zeile verworfen.</span><span class="sxs-lookup"><span data-stu-id="b57c7-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="b57c7-110">Beachten Sie außerdem, dass Sie nur eine bearbeiten können **DataRowView** zu einem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="b57c7-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="b57c7-111">Beim Aufrufen der **AddNew** oder **BeginEdit** Methode der **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** wird implizit aufgerufen werden, auf die ausstehende Zeile.</span><span class="sxs-lookup"><span data-stu-id="b57c7-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="b57c7-112">Wenn **EndEdit** wird aufgerufen, die vorgenommenen Änderungen werden auf die zugrunde liegende **DataTable** und kann später übernommen oder abgelehnt wird, mit der **AcceptChanges** oder  **RejectChanges** Methoden die **DataTable**, **DataSet**, oder **DataRow** Objekt.</span><span class="sxs-lookup"><span data-stu-id="b57c7-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="b57c7-113">Wenn **AllowNew** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie rufen die **AddNew** Methode der **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="b57c7-114">Wenn **AllowEdit** ist **"true"**, können Sie den Inhalt der Ändern einer **DataRow** über die **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="b57c7-115">Sie können überprüfen, ob Änderungen an der zugrunde liegenden Zeile mit **DataRowView.EndEdit** oder ablehnen die Änderungen mit **DataRowView.CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="b57c7-116">Beachten Sie, dass jeweils nur eine Zeile bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b57c7-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="b57c7-117">Beim Aufrufen der **AddNew** oder **BeginEdit** Methoden die **DataRowView** während eine ausstehende Zeile vorhanden ist, **EndEdit** implizit für aufgerufen die ausstehende Zeile.</span><span class="sxs-lookup"><span data-stu-id="b57c7-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="b57c7-118">Wenn **EndEdit** aufgerufen wird, vorgeschlagene Änderungen befinden sich der **aktuelle** Zeilenversion der zugrunde liegenden **DataRow** und kann später übernommen oder abgelehnt wird, verwenden die  **AcceptChanges** oder **RejectChanges** Methoden die **DataTable**, **DataSet**, oder **DataRow** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="b57c7-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="b57c7-119">Wenn **AllowEdit** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie versuchen, einen Wert im Ändern der **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="b57c7-120">Wenn eine vorhandene **DataRowView** bearbeitet wird, Ereignisse der zugrunde liegenden **DataTable** weiterhin mit den vorgeschlagenen Änderungen ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="b57c7-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="b57c7-121">Beachten Sie, dass beim Aufrufen **EndEdit** oder **CancelEdit** für den zugrunde liegenden **DataRow**, ausstehende Änderungen angewendet oder abgebrochen wird, unabhängig davon, ob  **EndEdit** oder **CancelEdit** aufgerufen wird, auf die **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="b57c7-122">Wenn **AllowDelete** ist **"true"**, können Sie Zeilen aus Löschen der **"DataView"** mithilfe der **löschen** Methode der **"DataView"**  oder **DataRowView** Objekt und die Zeilen werden gelöscht, aus der zugrunde liegenden **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="b57c7-123">Später bestätigen oder Ablehnen der Löschvorgänge über können **AcceptChanges** oder **RejectChanges** bzw..</span><span class="sxs-lookup"><span data-stu-id="b57c7-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="b57c7-124">Wenn **AllowDelete** ist **"false"**, eine Ausnahme wird ausgelöst, wenn Sie rufen die **löschen** Methode der **"DataView"** oder  **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="b57c7-125">Deaktiviert im folgenden Codebeispiel wird die Verwendung der **"DataView"** zum Löschen von Zeilen und fügt eine neue Zeile der zugrunde liegenden Tabelle mithilfe der **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="b57c7-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b57c7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b57c7-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="b57c7-127">DataViews</span><span class="sxs-lookup"><span data-stu-id="b57c7-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="b57c7-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b57c7-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
