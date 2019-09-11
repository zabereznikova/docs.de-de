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
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856114"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Vorgehensweise: Festlegen des Textinhalts eines TextBox-Steuerelements

In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Controls.TextBox.Text%2A> die-Eigenschaft verwendet wird, um den ursprünglichen <xref:System.Windows.Controls.TextBox> Text Inhalt eines-Steuer Elements festzulegen.

> [!NOTE]
> <xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox.Text%2A> Obwohl die- `<TextBox.Text>` [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Version des Beispiels die-Tags um den Text der einzelnen Schaltflächen Inhalte verwenden könnte, ist dies nicht notwendig, da das-Attribut auf die Eigenschaft anwendet. . Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../advanced/xaml-overview-wpf.md).

## <a name="example"></a>Beispiel

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Beispiel

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
