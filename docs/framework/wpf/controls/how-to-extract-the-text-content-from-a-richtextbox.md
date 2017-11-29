---
title: 'Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f24b71bcb5f013c4b7054dd0948e5f2709230a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox
In diesem Beispiel wird gezeigt, wie auf den Inhalt des Extrahieren einer <xref:System.Windows.Controls.RichTextBox> als nur-Text.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> Steuerelement mit einfachem Inhalt.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert eine Methode, die eine <xref:System.Windows.Controls.RichTextBox> als Argument und eine Zeichenfolge zurückgibt, die nur-Text-Inhalt, der die <xref:System.Windows.Controls.RichTextBox>.  
  
 Die Methode erstellt ein neues <xref:System.Windows.Documents.TextRange> aus dem Inhalt der <xref:System.Windows.Controls.RichTextBox>unter Verwendung der <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> an, dass der Bereich des Inhalts zu extrahieren.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A>und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> Eigenschaften jedes Zurückgeben einer <xref:System.Windows.Documents.TextPointer>, auf die zugrunde liegende FlowDocument, die den Inhalt darstellt und verfügbar sind die <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange>bietet eine Texteigenschaft, die zurückgibt, die nur-Text-Teile der <xref:System.Windows.Documents.TextRange> als Zeichenfolge.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
