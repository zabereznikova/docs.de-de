---
title: 'Gewusst wie: Navigieren durch Daten in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d99d794164307cb22c5dfc89d6c9c227aa457a59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="e56da-102">Gewusst wie: Navigieren durch Daten in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e56da-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="e56da-103">In einer Windows-Anwendung ist die einfachste Möglichkeit zum Navigieren durch Datensätze in einer Datenquelle zum Binden einer <xref:System.Windows.Forms.BindingSource> -Komponente an die Datenquelle ein, und Binden von Steuerelementen an die <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e56da-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="e56da-104">Anschließend können Sie die integrierte Navigationsmethode auf die <xref:System.Windows.Forms.BindingSource> solche eine <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> und <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span><span class="sxs-lookup"><span data-stu-id="e56da-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="e56da-105">Mit diesen Methoden wird angepasst, die <xref:System.Windows.Forms.BindingSource.Position%2A> und <xref:System.Windows.Forms.BindingSource.Current%2A> Eigenschaften der <xref:System.Windows.Forms.BindingSource> entsprechend.</span><span class="sxs-lookup"><span data-stu-id="e56da-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="e56da-106">Sie können auch nach einem Element zu suchen und es als aktuelles Element festgelegt, durch Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e56da-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="e56da-107">Erhöht die Position in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="e56da-107">To increment the position in a data source</span></span>  
  
1.  <span data-ttu-id="e56da-108">Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft von der <xref:System.Windows.Forms.BindingSource> für die gebundenen Daten auf die Position des Datensatzes zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="e56da-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="e56da-109">Im folgende Beispiel wird die Verwendung der <xref:System.Windows.Forms.BindingSource.MoveNext%2A> Methode der <xref:System.Windows.Forms.BindingSource> zur Erhöhung der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft bei der `nextButton` geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="e56da-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="e56da-110">Die <xref:System.Windows.Forms.BindingSource> zugeordnet ist die `Customers` Tabelle eines Datasets `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="e56da-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e56da-111">Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft auf einen Wert über den ersten oder letzten Datensatz führt nicht zu einem Fehler, als die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] nicht können Sie die Position auf einen Wert außerhalb des gültigen Bereichs der Liste festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e56da-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="e56da-112">Wenn es wichtig, in der Anwendung ist zu ermitteln, ob Sie hinter dem ersten oder letzten Datensatz überschritten haben, schließen Sie Logik zum Überprüfen, ob Sie die Anzahl der Elemente überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e56da-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="e56da-113">Überprüft, ob Sie am Ende oder Anfang bestanden haben</span><span class="sxs-lookup"><span data-stu-id="e56da-113">To check whether you have passed the end or beginning</span></span>  
  
1.  <span data-ttu-id="e56da-114">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.BindingSource.PositionChanged>-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e56da-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="e56da-115">In den Handler auf können Sie testen, ob der vorgeschlagene Positionswert wird die Anzahl der tatsächlichen Daten überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="e56da-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="e56da-116">Im folgende Beispiel wird veranschaulicht, wie Sie testen können, ob Sie das letzte Datenelement erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="e56da-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="e56da-117">Im Beispiel, wenn Sie beim letzten Element sind die **Weiter** Formular auf die Schaltfläche ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e56da-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e56da-118">Beachten Sie, dass, sollten Sie die Liste, die Sie im Code navigieren ändern, müssen Sie erneut aktivieren die **Weiter** Schaltfläche, sodass Benutzer die gesamte Länge der neuen Liste durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="e56da-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="e56da-119">Achten Sie außerdem darauf, die oben genannten <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignis für den jeweiligen <xref:System.Windows.Forms.BindingSource> Sie arbeiten mit seiner Ereignisbehandlungsmethode verknüpft werden muss.</span><span class="sxs-lookup"><span data-stu-id="e56da-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="e56da-120">Im folgenden ist ein Beispiel für eine Methode zur Behandlung der <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignis:</span><span class="sxs-lookup"><span data-stu-id="e56da-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="e56da-121">Um nach einem Element zu suchen, und legen Sie es als aktuelles Element</span><span class="sxs-lookup"><span data-stu-id="e56da-121">To find an item and set it as the current item</span></span>  
  
1.  <span data-ttu-id="e56da-122">Suchen Sie den Datensatz, als das aktuelle Element festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e56da-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="e56da-123">Hierzu können Sie mithilfe der <xref:System.Windows.Forms.BindingSource.Find%2A> Methode der <xref:System.Windows.Forms.BindingSource>, wenn die Datenquelle implementiert <xref:System.ComponentModel.IBindingList>.</span><span class="sxs-lookup"><span data-stu-id="e56da-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="e56da-124">Einige Beispiele für Daten Datenquellen implementiert, <xref:System.ComponentModel.IBindingList> sind <xref:System.ComponentModel.BindingList%601> und <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="e56da-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e56da-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e56da-125">See Also</span></span>  
 [<span data-ttu-id="e56da-126">Von Windows Forms unterstützte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="e56da-126">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [<span data-ttu-id="e56da-127">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e56da-127">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="e56da-128">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e56da-128">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="e56da-129">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e56da-129">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
