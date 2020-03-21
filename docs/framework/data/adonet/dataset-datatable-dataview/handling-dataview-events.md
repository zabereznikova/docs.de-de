---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151103"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="721c0-102">Behandeln von DataView-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="721c0-102">Handling DataView Events</span></span>
<span data-ttu-id="721c0-103">Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="721c0-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="721c0-104">Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="721c0-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="721c0-105">Das **ListChanged-Ereignis** benachrichtigt Sie auch, wenn sich die Liste der angezeigten Zeilen aufgrund der Anwendung einer neuen Sortierreihenfolge oder eines Filters erheblich geändert hat.</span><span class="sxs-lookup"><span data-stu-id="721c0-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="721c0-106">Das **ListChanged-Ereignis** implementiert den **ListChangedEventHandler-Delegaten** des <xref:System.ComponentModel> <xref:System.ComponentModel.ListChangedEventArgs> Namespace und nimmt als Eingabe ein Objekt an.</span><span class="sxs-lookup"><span data-stu-id="721c0-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="721c0-107">Sie können mithilfe des <xref:System.ComponentModel.ListChangedType> Enumerationswerts in der **ListChangedType-Eigenschaft** des **ListChangedEventArgs-Objekts** bestimmen, welche Art von Änderung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="721c0-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="721c0-108">Bei Änderungen, die das Hinzufügen, Löschen oder Verschieben von Zeilen beinhalten, kann über die **NewIndex-Eigenschaft** des **ListChangedEventArgs-Objekts** auf den neuen Index der hinzugefügten oder verschobenen Zeile und auf den vorherigen Index der gelöschten Zeile zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="721c0-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="721c0-109">Im Fall einer verschobenen Zeile kann mit der **OldIndex-Eigenschaft** des **ListChangedEventArgs-Objekts** auf den vorherigen Index der verschobenen Zeile zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="721c0-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="721c0-110">**Der DataViewManager** macht auch ein **ListChanged-Ereignis** verfügbar, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde oder ob eine Änderung an der **Relations-Auflistung** des zugrunde liegenden **DataSet**vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="721c0-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="721c0-111">Das folgende Codebeispiel zeigt, wie Sie einen **ListChanged-Ereignishandler** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="721c0-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="721c0-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="721c0-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="721c0-113">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="721c0-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="721c0-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="721c0-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
