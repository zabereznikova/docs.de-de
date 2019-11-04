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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="91f84-102">Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="91f84-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="91f84-103">Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft verwenden, um den ursprünglichen Text Inhalt eines <xref:System.Windows.Controls.TextBox> Steuer Elements festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91f84-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="91f84-104">Obwohl in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Version des Beispiels die `<TextBox.Text>` Tags um den Text der <xref:System.Windows.Controls.TextBox> Inhalte der Schaltfläche verwendet werden können, ist dies nicht notwendig, da das <xref:System.Windows.Markup.ContentPropertyAttribute>-Attribut von der <xref:System.Windows.Controls.TextBox> auf die <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="91f84-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="91f84-105">Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="91f84-105">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="91f84-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91f84-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="91f84-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91f84-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="91f84-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91f84-108">See also</span></span>

- [<span data-ttu-id="91f84-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="91f84-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="91f84-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="91f84-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
