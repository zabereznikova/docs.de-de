---
title: "Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Inhalt, Extrahieren"
  - "Extrahieren von Textinhalt"
  - "RichTextBox-Steuerelement, Extrahieren von Textinhalt"
  - "Textinhalt, Extrahieren"
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Extrahieren von Textinhalt aus einer RichTextBox
In diesem Beispiel wird gezeigt, wie der Inhalt von <xref:System.Windows.Controls.RichTextBox> als Nur\-Text extrahiert wird.  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox>\-Steuerelement mit einfachem Inhalt.  
  
 [!code-xml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## Beispiel  
 Der folgende Code implementiert eine Methode, die <xref:System.Windows.Controls.RichTextBox> als Argument verwendet und eine Zeichenfolge zurückgibt, die den Nur\-Text\-Inhalt von <xref:System.Windows.Controls.RichTextBox> darstellt.  
  
 Die Methode erstellt einen neuen <xref:System.Windows.Documents.TextRange> aus dem Inhalt von <xref:System.Windows.Controls.RichTextBox>, wobei <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> und <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> verwendet werden, um den Bereich des zu extrahierenden Inhalts anzugeben  Die <xref:System.Windows.Documents.FlowDocument.ContentStart%2A>\-Eigenschaft und die <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>\-Eigenschaft geben jeweils einen <xref:System.Windows.Documents.TextPointer>, zurück; auf sie kann über das zugrunde liegende FlowDocument zugegriffen werden, das den Inhalt von <xref:System.Windows.Controls.RichTextBox> darstellt.  <xref:System.Windows.Documents.TextRange> stellt eine Texteigenschaft bereit, die die Nur\-Text\-Teile vom <xref:System.Windows.Documents.TextRange> als eine Zeichenfolge zurückgibt.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)