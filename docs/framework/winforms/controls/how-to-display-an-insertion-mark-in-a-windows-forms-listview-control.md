---
title: 'Vorgehensweise: Anzeigen einer Einfügemarke in ein ListView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 199e0e232e2d391c2e7e0d70757f1f414cce5498
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261452"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="1b625-102">Vorgehensweise: Anzeigen einer Einfügemarke in ein ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b625-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="1b625-103">Die Einfügemarke im <xref:System.Windows.Forms.ListView>-Steuerelement zeigt Benutzern die Stelle an, an der mit der Maus gezogene Elemente eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1b625-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="1b625-104">Wenn ein Benutzer ein Element an eine Stelle zwischen zwei anderen Elementen zieht, gibt die Einfügemarke die erwartete neue Position des Elements an.</span><span class="sxs-lookup"><span data-stu-id="1b625-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b625-105">Das Einfügemarkenfeature steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="1b625-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1b625-106">Unter früheren Betriebssystemen hat Code in Zusammenhang mit der Einfügemarke keine Auswirkungen, und die Einfügemarke wird daher nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b625-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="1b625-107">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="1b625-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="1b625-108">In der folgenden Abbildung ist eine Einfügemarke dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1b625-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="1b625-109">![Eine ListView-Einfügemarke](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "EinfügemarkeListView")</span><span class="sxs-lookup"><span data-stu-id="1b625-109">![A ListView Insertion Mark](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="1b625-110">Im folgenden Codebeispiel wird die Verwendung dieser Funktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1b625-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b625-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b625-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b625-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1b625-112">Compiling the Code</span></span>  
 <span data-ttu-id="1b625-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1b625-113">This example requires:</span></span>  
  
-   <span data-ttu-id="1b625-114">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="1b625-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1b625-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1b625-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1b625-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="1b625-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b625-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b625-117">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="1b625-118">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b625-118">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [<span data-ttu-id="1b625-119">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b625-119">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="1b625-120">Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b625-120">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
