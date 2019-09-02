---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b3a1077bff9bf457b4aef0b05357d4a9260f8973
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204825"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="2adb3-102">Behandeln von DataView-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="2adb3-102">Handling DataView Events</span></span>
<span data-ttu-id="2adb3-103">Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2adb3-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="2adb3-104">Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="2adb3-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="2adb3-105">Das **ListChanged** -Ereignis benachrichtigt Sie auch, wenn sich die Liste der Zeilen, die Sie anzeigen, aufgrund der Anwendung einer neuen Sortierreihenfolge oder eines Filters erheblich geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2adb3-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="2adb3-106">Das **ListChanged** -Ereignis implementiert den **listchangedebug-thandler** -Delegaten des <xref:System.ComponentModel> -Namespace und übernimmt als Eingabe ein <xref:System.ComponentModel.ListChangedEventArgs> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="2adb3-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="2adb3-107">Sie können mit dem <xref:System.ComponentModel.ListChangedType> -Enumerationswert in der **ListChangedType** -Eigenschaft des **ListChangedEventArgs** -Objekts ermitteln, welche Art von Änderung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2adb3-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="2adb3-108">Bei Änderungen, die das Hinzufügen, löschen oder Verschieben von Zeilen einschließen, kann auf den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile mithilfe der Eigenschaft " **netwindex** " des **ListChangedEventArgs** -Objekts zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2adb3-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="2adb3-109">Im Fall einer verschobene Zeile kann auf den vorherigen Index der verschobene Zeile mithilfe der **OldIndex** -Eigenschaft des **ListChangedEventArgs** -Objekts zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2adb3-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="2adb3-110">Der **DataViewManager** macht auch ein **ListChanged** -Ereignis verfügbar, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde, oder wenn eine Änderung an der **Beziehungs** Auflistung des zugrunde liegenden **DataSets**vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="2adb3-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="2adb3-111">Im folgenden Codebeispiel wird gezeigt, wie ein **ListChanged** -Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2adb3-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2adb3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2adb3-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="2adb3-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="2adb3-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="2adb3-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="2adb3-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
