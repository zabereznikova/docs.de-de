---
title: "Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements | Microsoft Docs"
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
  - "Textinhalt, Festlegen"
  - "TextBox-Steuerelement, Festlegen von Textinhalt"
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen des Textinhalts eines TextBox-Steuerelements
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft verwendet wird, um die ursprünglichen Textinhalte eines <xref:System.Windows.Controls.TextBox>\-Steuerelements festzulegen.  
  
 **Hinweis** In der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Version des Beispiels könnten zwar die `<TextBox.Text>`\-Tags um den Text des <xref:System.Windows.Controls.TextBox>\-Inhalts der einzelnen Schaltflächen verwendet werden, dies ist jedoch nicht erforderlich, da von <xref:System.Windows.Controls.TextBox> das <xref:System.Windows.Markup.ContentPropertyAttribute>\-Attribut auf die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft angewendet wird.  Weitere Informationen finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
## Beispiel  
 [!code-xml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## Beispiel  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)