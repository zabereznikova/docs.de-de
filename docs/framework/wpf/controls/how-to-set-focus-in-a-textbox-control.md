---
title: 'Vorgehensweise: Setzen des Fokus in einem TextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: f4ba367ea9bdfcd6dbab7a5015472ec33adfe46f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024351"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="7dcf1-102">Vorgehensweise: Setzen des Fokus in einem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7dcf1-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="7dcf1-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.UIElement.Focus%2A> Methode zum Festlegen des Fokus auf ein <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7dcf1-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dcf1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dcf1-104">Example</span></span>  
 <span data-ttu-id="7dcf1-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel beschreibt eine einfache <xref:System.Windows.Controls.TextBox> Steuerelement mit dem Namen *TbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="7dcf1-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="7dcf1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dcf1-106">Example</span></span>  
 <span data-ttu-id="7dcf1-107">Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Focus%2A> Methode zum Festlegen des Fokus auf die <xref:System.Windows.Controls.TextBox> Steuerelement mit dem Namen *TbFocusMe*.</span><span class="sxs-lookup"><span data-stu-id="7dcf1-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="7dcf1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dcf1-108">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="7dcf1-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="7dcf1-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="7dcf1-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7dcf1-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
