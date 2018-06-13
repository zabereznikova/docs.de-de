---
title: 'Gewusst wie: Setzen des Fokus in einem TextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: 1bda01a3d330ad384c2f922ff3c7679e10d0f148
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552538"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="2322f-102">Gewusst wie: Setzen des Fokus in einem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2322f-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="2322f-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.UIElement.Focus%2A> -Methode zum Festlegen des Fokus auf ein <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2322f-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2322f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2322f-104">Example</span></span>  
 <span data-ttu-id="2322f-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel beschrieben, eine einfache <xref:System.Windows.Controls.TextBox> Steuerelement namens *TbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="2322f-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="2322f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2322f-106">Example</span></span>  
 <span data-ttu-id="2322f-107">Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Focus%2A> Methode, um den Fokus der <xref:System.Windows.Controls.TextBox> Steuerelement mit dem Namen *TbFocusMe*.</span><span class="sxs-lookup"><span data-stu-id="2322f-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="2322f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2322f-108">See Also</span></span>  
 <xref:System.Windows.UIElement.Focusable%2A>  
 <xref:System.Windows.UIElement.IsFocused%2A>  
 [<span data-ttu-id="2322f-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="2322f-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="2322f-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="2322f-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
