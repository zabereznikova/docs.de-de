---
title: 'Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 1bb2233cf9e288ae89ebb8cab3df4f6451dc8eed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526695"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="7de17-102">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="7de17-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="7de17-103">Sie können Windows Forms <xref:System.Windows.Forms.TabControl> andere Steuerelemente in einer strukturierten Weise angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7de17-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="7de17-104">Das folgende Verfahren zeigt, wie eine Schaltfläche auf der ersten Registerkarte hinzufügen. Informationen zum Hinzufügen eines Symbols auf der Bezeichnungsteil einer Registerkartenseite finden Sie unter [Vorgehensweise: Ändern der Darstellung der TabControl in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="7de17-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="7de17-105">So fügen Sie ein Steuerelement programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="7de17-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="7de17-106">Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem Sie die <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="7de17-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7de17-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7de17-107">See Also</span></span>  
 [<span data-ttu-id="7de17-108">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7de17-108">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="7de17-109">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7de17-109">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="7de17-110">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7de17-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="7de17-111">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="7de17-111">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="7de17-112">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7de17-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
