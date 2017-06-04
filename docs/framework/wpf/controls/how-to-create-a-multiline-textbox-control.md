---
title: "Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements | Microsoft Docs"
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
  - "TextBox-Steuerelement, Mehrere Textzeilen"
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements
Im folgenden Beispiel wird verdeutlicht, wie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ein <xref:System.Windows.Controls.TextBox>\-Steuerelement definiert wird, das sich automatisch vergrößert, um mehrere Zeilen Text aufzunehmen.  
  
## Beispiel  
 Durch Festlegen des <xref:System.Windows.Controls.TextBox.TextWrapping%2A>\-Attributs auf **Wrap** wird eingegebener Text auf eine neue Zeile umbrochen, wenn der Rand des <xref:System.Windows.Controls.TextBox>\-Steuerelements erreicht wird. Dabei wird das <xref:System.Windows.Controls.TextBox>\-Steuerelement bei Bedarf automatisch vergrößert, um die neue Zeile aufzunehmen.  
  
 Durch Festlegen des <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>\-Attributs auf **true** wird eine neue Zeile eingefügt, wenn die EINGABETASTE gedrückt wird, wodurch ggf. auch wieder das <xref:System.Windows.Controls.TextBox> automatisch angepasst wird, um die neue Zeile aufzunehmen.  
  
 Das <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>\-Attribut fügt dem <xref:System.Windows.Controls.TextBox> eine Bildlaufleiste hinzu, sodass für die Inhalte des <xref:System.Windows.Controls.TextBox>\-Elements ein Bildlauf durchgeführt werden kann, wenn das <xref:System.Windows.Controls.TextBox> die Größe des umgebenden Rahmens oder Fensters überschreitet.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## Siehe auch  
 <xref:System.Windows.TextWrapping>   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)