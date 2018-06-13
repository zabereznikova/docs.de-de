---
title: 'Gewusst wie: Ändern der Typografie von Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: fcc9c894970934bb5a69debef2f4e38297f82198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542928"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="bc013-102">Gewusst wie: Ändern der Typografie von Text</span><span class="sxs-lookup"><span data-stu-id="bc013-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="bc013-103">Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Documents.TextElement.Typography%2A> -Attribut mit <xref:System.Windows.Documents.Paragraph> wie das Beispielelement.</span><span class="sxs-lookup"><span data-stu-id="bc013-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc013-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc013-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="bc013-105">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="bc013-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="bc013-106">![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="bc013-106">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="bc013-107">Im Gegensatz dazu zeigt die folgende Abbildung, wie ein ähnliches Beispiel mit typografischen Standardeigenschaften gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="bc013-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="bc013-108">![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="bc013-108">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc013-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc013-109">Example</span></span>  
 <span data-ttu-id="bc013-110">Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Controls.TextBox.Typography%2A> Eigenschaft programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="bc013-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="bc013-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc013-111">See Also</span></span>  
 [<span data-ttu-id="bc013-112">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="bc013-112">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
