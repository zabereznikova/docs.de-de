---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten TextBox-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517174"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="fcc12-102">Vorgehensweise: Erstellen eines schreibgeschützten TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="fcc12-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="fcc12-103">Dieses Beispiel zeigt, wie Sie konfigurieren eine <xref:System.Windows.Controls.TextBox> Steuerelement, damit keine Benutzereingaben oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="fcc12-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc12-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcc12-104">Example</span></span>  
 <span data-ttu-id="fcc12-105">Um zu verhindern, dass Benutzer ändern des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, legen Sie die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> -Attribut auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="fcc12-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="fcc12-106">Die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Attribut wirkt sich auf nur die Benutzereingabe; er hat keine Auswirkungen auf Text, legen Sie in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beschreibung des eine <xref:System.Windows.Controls.TextBox> -Steuerelement oder Text programmgesteuert durch Festlegen der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fcc12-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="fcc12-107">Der Standardwert von <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> ist **"false"**.</span><span class="sxs-lookup"><span data-stu-id="fcc12-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc12-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcc12-108">See also</span></span>
- [<span data-ttu-id="fcc12-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="fcc12-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="fcc12-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fcc12-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
