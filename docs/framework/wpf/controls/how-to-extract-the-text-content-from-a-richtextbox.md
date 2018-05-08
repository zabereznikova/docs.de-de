---
title: 'Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 309fe15c76c17a79e11341f3a50c0bf5a7a2cc21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox
In diesem Beispiel wird gezeigt, wie auf den Inhalt des Extrahieren einer <xref:System.Windows.Controls.RichTextBox> als nur-Text.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> Steuerelement mit einfachem Inhalt.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert eine Methode, die eine <xref:System.Windows.Controls.RichTextBox> als Argument und eine Zeichenfolge zurückgibt, die nur-Text-Inhalt, der die <xref:System.Windows.Controls.RichTextBox>.  
  
 Die Methode erstellt ein neues <xref:System.Windows.Documents.TextRange> aus dem Inhalt der <xref:System.Windows.Controls.RichTextBox>unter Verwendung der <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> an, dass der Bereich des Inhalts zu extrahieren.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> Eigenschaften jedes Zurückgeben einer <xref:System.Windows.Documents.TextPointer>, auf die zugrunde liegende FlowDocument, die den Inhalt darstellt und verfügbar sind die <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> bietet eine Texteigenschaft, die zurückgibt, die nur-Text-Teile der <xref:System.Windows.Documents.TextRange> als Zeichenfolge.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
