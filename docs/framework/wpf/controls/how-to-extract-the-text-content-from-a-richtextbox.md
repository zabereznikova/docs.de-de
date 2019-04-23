---
title: 'Vorgehensweise: Extrahieren von Textinhalten aus einem RichTextBox-Objekt'
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
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086116"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Vorgehensweise: Extrahieren von Textinhalten aus einem RichTextBox-Objekt
Dieses Beispiel zeigt, wie Sie den Inhalt des Extrahieren einer <xref:System.Windows.Controls.RichTextBox> als nur-Text.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> -Steuerelement mit einfachem Inhalt.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert eine Methode, verwendet eine <xref:System.Windows.Controls.RichTextBox> als Argument und gibt eine Zeichenfolge mit der nur-Text-Inhalt, der die <xref:System.Windows.Controls.RichTextBox>.  
  
 Die Methode erstellt ein neues <xref:System.Windows.Documents.TextRange> aus dem Inhalt der <xref:System.Windows.Controls.RichTextBox>unter Verwendung der <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> an, dass der Bereich des Inhalts extrahiert.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> Eigenschaften jedes Zurückgeben einer <xref:System.Windows.Documents.TextPointer>, auf das zugrunde liegende FlowDocument, die den Inhalt des darstellt und verfügbar sind die <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> Stellt eine Text-Eigenschaft, die die Teile für nur-Text zurückgibt. die <xref:System.Windows.Documents.TextRange> als Zeichenfolge.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über RichTextBox](richtextbox-overview.md)
- [Übersicht über TextBox](textbox-overview.md)
