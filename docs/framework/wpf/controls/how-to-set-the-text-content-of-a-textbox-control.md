---
title: 'Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 9b16f2d99295a28725255361b0be3ef7f4245fd2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459306"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements

Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft verwenden, um den ursprünglichen Text Inhalt eines <xref:System.Windows.Controls.TextBox> Steuer Elements festzulegen.

> [!NOTE]
> Obwohl in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Version des Beispiels die `<TextBox.Text>` Tags um den Text der <xref:System.Windows.Controls.TextBox> Inhalte der Schaltfläche verwendet werden können, ist dies nicht notwendig, da das <xref:System.Windows.Markup.ContentPropertyAttribute>-Attribut von der <xref:System.Windows.Controls.TextBox> auf die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft angewendet wird. Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Beispiel

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Beispiel

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
