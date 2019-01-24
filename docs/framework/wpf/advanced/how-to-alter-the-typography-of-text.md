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
ms.openlocfilehash: f04c873e542ad02c1d2a20b770ded4464af7a6d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645404"
---
# <a name="how-to-alter-the-typography-of-text"></a>Gewusst wie: Ändern der Typografie von Text
Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Documents.TextElement.Typography%2A> -Attributs unter Verwendung <xref:System.Windows.Documents.Paragraph> als Beispielelement.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 Im Gegensatz dazu zeigt die folgende Abbildung, wie ein ähnliches Beispiel mit typografischen Standardeigenschaften gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Controls.TextBox.Typography%2A> Eigenschaft programmgesteuert.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
