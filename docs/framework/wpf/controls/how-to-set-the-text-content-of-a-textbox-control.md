---
title: 'Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements'
description: Erfahren Sie, wie Sie die Text-Eigenschaft verwenden, um den ursprünglichen Text Inhalt eines Windows Presentation Foundation TextBox-Steuer Elements festzulegen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 41efb69e297b3c6fdb1203c358dcc72d7a9f806f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168043"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements

In diesem Beispiel wird gezeigt, wie die-Eigenschaft verwendet wird <xref:System.Windows.Controls.TextBox.Text%2A> , um den ursprünglichen Text Inhalt eines-Steuer Elements festzulegen <xref:System.Windows.Controls.TextBox> .

> [!NOTE]
> Obwohl die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Version des Beispiels die `<TextBox.Text>` -Tags um den Text der einzelnen Schaltflächen Inhalte verwenden könnte <xref:System.Windows.Controls.TextBox> , ist dies nicht notwendig, da das- <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Markup.ContentPropertyAttribute> Attribut auf die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft anwendet. Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Beispiel

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Beispiel

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
