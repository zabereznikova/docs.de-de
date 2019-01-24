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
ms.openlocfilehash: 1ab7fa5f5ce895d163e3db3dd020fee3f29b7153
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590707"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a>Vorgehensweise: Setzen des Fokus in einem TextBox-Steuerelement
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.UIElement.Focus%2A> Methode zum Festlegen des Fokus auf ein <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel beschreibt eine einfache <xref:System.Windows.Controls.TextBox> Steuerelement mit dem Namen *TbFocusMe*  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Focus%2A> Methode zum Festlegen des Fokus auf die <xref:System.Windows.Controls.TextBox> Steuerelement mit dem Namen *TbFocusMe*.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
