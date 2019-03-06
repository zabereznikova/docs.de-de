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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="57e93-102">Vorgehensweise: Festlegen des Textinhalts eines TextBox-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="57e93-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="57e93-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.TextBox.Text%2A> -Eigenschaft zum Festlegen der anfänglichen Text-Inhalt, der eine <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="57e93-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="57e93-104">**Beachten Sie** zwar die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Version des Beispiels können die `<TextBox.Text>` Tags, um den Text der einzelnen Schaltflächen der <xref:System.Windows.Controls.TextBox> Inhalt, es ist nicht erforderlich da die <xref:System.Windows.Controls.TextBox> gilt die <xref:System.Windows.Markup.ContentPropertyAttribute> -Attribut auf die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="57e93-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="57e93-105">Weitere Informationen finden Sie unter [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="57e93-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57e93-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57e93-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="57e93-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57e93-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="57e93-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57e93-108">See also</span></span>
- [<span data-ttu-id="57e93-109">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="57e93-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="57e93-110">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="57e93-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
