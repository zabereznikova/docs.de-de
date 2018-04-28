---
title: 'Gewusst wie: Dynamisches Hinzufügen von ToolStrip-Elementen'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7af14c08bd5421cebb511aaf6d209236e80bc23e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="c69f2-102">Gewusst wie: Dynamisches Hinzufügen von ToolStrip-Elementen</span><span class="sxs-lookup"><span data-stu-id="c69f2-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="c69f2-103">Sie können die Auflistung von Menüelementen eines <xref:System.Windows.Forms.ToolStrip>-Steuerelements dynamisch ausfüllen, wenn das Menü geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c69f2-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c69f2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c69f2-104">Example</span></span>  
 <span data-ttu-id="c69f2-105">Im folgenden Codebeispiel wird veranschaulicht, wie Elemente einem <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement dynamisch hinzufügt werden.</span><span class="sxs-lookup"><span data-stu-id="c69f2-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="c69f2-106">Außerdem wird gezeigt, wie Sie die gleiche <xref:System.Windows.Forms.ContextMenuStrip> für drei verschiedene Steuerelemente im Formular wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="c69f2-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="c69f2-107">Im Beispiel füllt ein <xref:System.Windows.Forms.ToolStripDropDown.Opening>-Ereignishandler die Auflistung von Menüelementen aus.</span><span class="sxs-lookup"><span data-stu-id="c69f2-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="c69f2-108">Der <xref:System.Windows.Forms.ToolStripDropDown.Opening>-Ereignishandler überprüft die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> und die <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType>-Eigenschaften und fügt eine <xref:System.Windows.Forms.ToolStripItem> hinzu, die die Quellcodeverwaltung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c69f2-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c69f2-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c69f2-109">Compiling the Code</span></span>  
 <span data-ttu-id="c69f2-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c69f2-110">This example requires:</span></span>  
  
-   <span data-ttu-id="c69f2-111">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="c69f2-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c69f2-112">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c69f2-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c69f2-113">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="c69f2-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69f2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c69f2-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 [<span data-ttu-id="c69f2-115">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c69f2-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
