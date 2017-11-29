---
title: 'Gewusst wie: Anzeigen von seitlich ausgerichteten Registerkarten mit TabControl'
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
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d95e2aace6dc50b16aeea0fca02f0a27c37322c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="b2427-102">Gewusst wie: Anzeigen von seitlich ausgerichteten Registerkarten mit TabControl</span><span class="sxs-lookup"><span data-stu-id="b2427-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="b2427-103">Die <xref:System.Windows.Forms.TabControl.Alignment%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> unterstützt das vertikale Anzeigen von Registerkarten (entlang des linken oder rechten Rands des Steuerelements), im Gegensatz zu horizontal (am oberen oder unteren Rand des Steuerelements).</span><span class="sxs-lookup"><span data-stu-id="b2427-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="b2427-104">Standardmäßig führt diese vertikale Anzeige zu einer wenig benutzerfreundlichen Oberfläche, weil die <xref:System.Windows.Forms.TabPage.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.TabPage>-Objekts nicht auf der Registerkarte angezeigt wird, wenn visuelle Stile aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="b2427-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="b2427-105">Es ist außerdem keine direkte Möglichkeit zur Steuerung der Richtung des Texts auf der Registerkarte. Sie können Ownerdrawn in <xref:System.Windows.Forms.TabControl> verwenden, um die Oberfläche zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b2427-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="b2427-106">Das folgende Verfahren zeigt, wie rechtsbündig ausgerichtete Registerkarten gerendert werden, wobei der Registerkartentext von links nach rechts verläuft, indem Sie die Funktion "Ownerdrawn" verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2427-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="b2427-107">So zeigen Sie rechtsbündig ausgerichtete Registerkarten an</span><span class="sxs-lookup"><span data-stu-id="b2427-107">To display right-aligned tabs</span></span>  
  
1.  <span data-ttu-id="b2427-108">Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TabControl> hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2427-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2.  <span data-ttu-id="b2427-109">Legen Sie die <xref:System.Windows.Forms.TabControl.Alignment%2A>-Eigenschaft auf <xref:System.Windows.Forms.TabAlignment.Right> fest.</span><span class="sxs-lookup"><span data-stu-id="b2427-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3.  <span data-ttu-id="b2427-110">Legen Sie die <xref:System.Windows.Forms.TabControl.SizeMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.TabSizeMode.Fixed> fest, damit alle Registerkarten gleich breit sind.</span><span class="sxs-lookup"><span data-stu-id="b2427-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4.  <span data-ttu-id="b2427-111">Legen Sie die <xref:System.Windows.Forms.TabControl.ItemSize%2A>-Eigenschaft auf die gewünschte feste Größe für die Registerkarten fest.</span><span class="sxs-lookup"><span data-stu-id="b2427-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="b2427-112">Denken Sie daran, dass sich die <xref:System.Windows.Forms.TabControl.ItemSize%2A>-Eigenschaft verhält, als seien die Registerkarten am oberen Rand, obwohl sie rechtsbündig ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="b2427-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="b2427-113">Demzufolge müssen Sie, um die Registerkarten zu verbreitern, die <xref:System.Drawing.Size.Height%2A>-Eigenschaft ändern, und um sie höher zu machen, müssen Sie die <xref:System.Drawing.Size.Width%2A>-Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="b2427-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="b2427-114">Für ein optimales Ergebnis mit dem folgenden Codebeispiel legen Sie die <xref:System.Drawing.Size.Width%2A> der Registerkarten auf 25 und die <xref:System.Drawing.Size.Height%2A> auf 100 fest.</span><span class="sxs-lookup"><span data-stu-id="b2427-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5.  <span data-ttu-id="b2427-115">Legen Sie die <xref:System.Windows.Forms.TabControl.DrawMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> fest.</span><span class="sxs-lookup"><span data-stu-id="b2427-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6.  <span data-ttu-id="b2427-116">Definieren Sie einen Ereignishandler für das <xref:System.Windows.Forms.TabControl.DrawItem>-Ereignis des <xref:System.Windows.Forms.TabControl>, das den Text von links nach rechts rendert.</span><span class="sxs-lookup"><span data-stu-id="b2427-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b2427-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2427-117">See Also</span></span>  
 [<span data-ttu-id="b2427-118">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b2427-118">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
