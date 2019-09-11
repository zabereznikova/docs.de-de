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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="af048-102">Vorgehensweise: Festlegen des Textinhalts eines TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="af048-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="af048-103">In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Controls.TextBox.Text%2A> die-Eigenschaft verwendet wird, um den ursprünglichen <xref:System.Windows.Controls.TextBox> Text Inhalt eines-Steuer Elements festzulegen.</span><span class="sxs-lookup"><span data-stu-id="af048-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="af048-104"><xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox.Text%2A> Obwohl die- `<TextBox.Text>` [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Version des Beispiels die-Tags um den Text der einzelnen Schaltflächen Inhalte verwenden könnte, ist dies nicht notwendig, da das-Attribut auf die Eigenschaft anwendet. .</span><span class="sxs-lookup"><span data-stu-id="af048-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="af048-105">Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="af048-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="af048-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af048-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="af048-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af048-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="af048-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af048-108">See also</span></span>

- [<span data-ttu-id="af048-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="af048-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="af048-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="af048-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
