---
title: 'Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte'
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
ms.openlocfilehash: 42f0be64a6ac050fe8873588263b1faf7e2491a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710182"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="deb41-102">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="deb41-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="deb41-103">Sie können die Windows-Formulare verwenden <xref:System.Windows.Forms.TabControl> , um andere Steuerelemente in einer strukturierten Weise anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="deb41-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="deb41-104">Das folgende Verfahren veranschaulicht das Hinzufügen eine Schaltfläche auf der ersten Registerkarte. Informationen zum Hinzufügen eines Symbols auf die Bezeichnung eine Registerkarte, finden Sie unter [Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="deb41-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="deb41-105">Programmgesteuertes Hinzufügen des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="deb41-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="deb41-106">Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem die <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="deb41-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="deb41-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deb41-107">See also</span></span>
- [<span data-ttu-id="deb41-108">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="deb41-108">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="deb41-109">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="deb41-109">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="deb41-110">Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="deb41-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="deb41-111">Vorgehensweise: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="deb41-111">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="deb41-112">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="deb41-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
