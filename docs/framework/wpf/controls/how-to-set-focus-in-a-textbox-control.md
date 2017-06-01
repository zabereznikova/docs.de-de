---
title: "Gewusst wie: Setzen des Fokus in einem TextBox-Steuerelement | Microsoft Docs"
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
  - "Fokus, Festlegen"
  - "TextBox-Steuerelement, Festlegen des Fokus"
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Setzen des Fokus in einem TextBox-Steuerelement
In diesem Beispiel wird die Verwendung der <xref:System.Windows.UIElement.Focus%2A>\-Methode zum Setzen des Fokus auf ein <xref:System.Windows.Controls.TextBox>\-Steuerelement gezeigt.  
  
## Beispiel  
 Das folgende [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel beschreibt ein einfaches <xref:System.Windows.Controls.TextBox>\-Steuerelement mit dem Namen *tbFocusMe*.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## Beispiel  
 Im folgenden Beispiel wird mit der <xref:System.Windows.UIElement.Focus%2A>\-Methode der Fokus auf das <xref:System.Windows.Controls.TextBox>\-Steuerelement mit dem Namen *tbFocusMe* gesetzt.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## Siehe auch  
 <xref:System.Windows.UIElement.Focusable%2A>   
 <xref:System.Windows.UIElement.IsFocused%2A>   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)