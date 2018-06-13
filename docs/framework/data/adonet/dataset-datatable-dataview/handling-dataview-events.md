---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 9e67aef2a39a04adfdcc036c008aa80c9151c14b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762558"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="33efc-102">Behandeln von DataView-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="33efc-102">Handling DataView Events</span></span>
<span data-ttu-id="33efc-103">Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="33efc-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="33efc-104">Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="33efc-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="33efc-105">Die **ListChanged** Ereignis benachrichtigt Sie auch, wenn die Liste der angezeigten Zeilen aufgrund einer neuen Sortierreihenfolge oder ein Filter erheblich geändert hat.</span><span class="sxs-lookup"><span data-stu-id="33efc-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="33efc-106">Die **ListChanged** Ereignis implementiert die **ListChangedEventHandler** delegieren, der die <xref:System.ComponentModel> Namespaces und akzeptiert als Eingabe eine <xref:System.ComponentModel.ListChangedEventArgs> Objekt.</span><span class="sxs-lookup"><span data-stu-id="33efc-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="33efc-107">Können Sie ermitteln, welche Art von Änderung aufgetreten ist mit der <xref:System.ComponentModel.ListChangedType> Enumerationswert in der **ListChangedType** Eigenschaft von der **ListChangedEventArgs** Objekt.</span><span class="sxs-lookup"><span data-stu-id="33efc-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="33efc-108">Informationen zu Änderungen, bei denen hinzufügen, löschen oder Verschieben von Zeilen, den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile zugegriffen werden kann mithilfe der **NewIndex** Eigenschaft von der **ListChangedEventArgs** Objekt.</span><span class="sxs-lookup"><span data-stu-id="33efc-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="33efc-109">Eine verschobene Zeile der vorherige Index der verschobenen Zeile möglich, die mithilfe der **OldIndex** Eigenschaft von der **ListChangedEventArgs** Objekt.</span><span class="sxs-lookup"><span data-stu-id="33efc-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="33efc-110">Die **DataViewManager** macht auch eine **ListChanged** Ereignis, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde, oder um eine Änderung vorgenommen wurde die **Beziehungen** Auflistung von der zugrunde liegende **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="33efc-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="33efc-111">Das folgende Codebeispiel veranschaulicht das Hinzufügen einer **ListChanged** -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="33efc-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="33efc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33efc-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="33efc-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="33efc-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="33efc-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="33efc-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
