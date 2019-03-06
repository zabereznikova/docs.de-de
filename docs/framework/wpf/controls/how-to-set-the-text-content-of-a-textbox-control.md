---
title: 'Vorgehensweise: Festlegen des Textinhalts eines TextBox-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 6c0e6e53518d382a2052efa43993d418e35fa0f2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364124"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Vorgehensweise: Festlegen des Textinhalts eines TextBox-Steuerelements
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.TextBox.Text%2A> -Eigenschaft zum Festlegen der anfänglichen Text-Inhalt, der eine <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
 **Beachten Sie** zwar die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Version des Beispiels können die `<TextBox.Text>` Tags, um den Text der einzelnen Schaltflächen der <xref:System.Windows.Controls.TextBox> Inhalt, es ist nicht erforderlich da die <xref:System.Windows.Controls.TextBox> gilt die <xref:System.Windows.Markup.ContentPropertyAttribute> -Attribut auf die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft. Weitere Informationen finden Sie unter [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
