---
title: "Gewusst wie: Anzeigen einer Einfügemarke in einem ListView-Steuerelement in Windows Forms"
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
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd6df58495a03221d213d91dd8dc8178049c61c1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="565ba-102">Gewusst wie: Anzeigen einer Einfügemarke in einem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="565ba-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="565ba-103">Die Einfügemarke im <xref:System.Windows.Forms.ListView>-Steuerelement zeigt Benutzern die Stelle an, an der mit der Maus gezogene Elemente eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="565ba-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="565ba-104">Wenn ein Benutzer ein Element an eine Stelle zwischen zwei anderen Elementen zieht, gibt die Einfügemarke die erwartete neue Position des Elements an.</span><span class="sxs-lookup"><span data-stu-id="565ba-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="565ba-105">Das Einfügemarkenfeature steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="565ba-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="565ba-106">Unter früheren Betriebssystemen hat Code in Zusammenhang mit der Einfügemarke keine Auswirkungen, und die Einfügemarke wird daher nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="565ba-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="565ba-107">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="565ba-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="565ba-108">In der folgenden Abbildung ist eine Einfügemarke dargestellt:</span><span class="sxs-lookup"><span data-stu-id="565ba-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="565ba-109">![Eine ListView-Einfügemarke](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "EinfügemarkeListView")</span><span class="sxs-lookup"><span data-stu-id="565ba-109">![A ListView Insertion Mark](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="565ba-110">Im folgenden Codebeispiel wird die Verwendung dieser Funktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="565ba-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="565ba-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="565ba-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="565ba-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="565ba-112">Compiling the Code</span></span>  
 <span data-ttu-id="565ba-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="565ba-113">This example requires:</span></span>  
  
-   <span data-ttu-id="565ba-114">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="565ba-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="565ba-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="565ba-115">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="565ba-116">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="565ba-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="565ba-117">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="565ba-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565ba-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="565ba-118">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [<span data-ttu-id="565ba-119">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="565ba-119">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="565ba-120">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="565ba-120">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="565ba-121">Windows XP-Features und Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="565ba-121">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="565ba-122">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="565ba-122">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
