---
title: 'Vorgehensweise: Anzeigen einer Einfügemarke in einem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: f5de00fd41b24fc1a7f1ff4484c3a126e98952a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967835"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="e676d-102">Vorgehensweise: Anzeigen einer Einfügemarke in einem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e676d-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="e676d-103">Die Einfügemarke im <xref:System.Windows.Forms.ListView>-Steuerelement zeigt Benutzern die Stelle an, an der mit der Maus gezogene Elemente eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e676d-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="e676d-104">Wenn ein Benutzer ein Element an eine Stelle zwischen zwei anderen Elementen zieht, gibt die Einfügemarke die erwartete neue Position des Elements an.</span><span class="sxs-lookup"><span data-stu-id="e676d-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e676d-105">Das Einfügemarkenfeature steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="e676d-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e676d-106">Unter früheren Betriebssystemen hat Code in Zusammenhang mit der Einfügemarke keine Auswirkungen, und die Einfügemarke wird daher nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e676d-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="e676d-107">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="e676d-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="e676d-108">In der folgenden Abbildung ist eine Einfügemarke dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e676d-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="e676d-109">![Screenshot, der eine ListView-Einfügemarke anzeigt.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "Listviewinsertion")</span><span class="sxs-lookup"><span data-stu-id="e676d-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="e676d-110">Im folgenden Codebeispiel wird die Verwendung dieser Funktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e676d-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e676d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e676d-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e676d-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e676d-112">Compiling the Code</span></span>  
 <span data-ttu-id="e676d-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e676d-113">This example requires:</span></span>  
  
- <span data-ttu-id="e676d-114">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="e676d-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e676d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e676d-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="e676d-116">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e676d-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="e676d-117">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e676d-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="e676d-118">Exemplarische Vorgehensweise: Ausführen eines Drag & Drop-Vorgangs in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e676d-118">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
