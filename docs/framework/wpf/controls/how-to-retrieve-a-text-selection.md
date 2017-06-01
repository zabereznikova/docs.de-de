---
title: "Gewusst wie: Abrufen einer Textauswahl | Microsoft Docs"
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
  - "Abrufen von Text"
  - "Text, Abrufen"
  - "TextBox-Steuerelement, Abrufen von Text"
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Abrufen einer Textauswahl
In diesem Beispiel wird eine Möglichkeit veranschaulicht, um mit der <xref:System.Windows.Controls.TextBox.SelectedText%2A>\-Eigenschaft Text abzurufen, den der Benutzer in einem <xref:System.Windows.Controls.TextBox>\-Steuerelement ausgewählt hat.  
  
## Beispiel  
 Im folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel wird die Definition eines <xref:System.Windows.Controls.TextBox>\-Steuerelements dargestellt, das auswählbaren Text enthält sowie ein <xref:System.Windows.Controls.Button>\-Steuerelement mit einer angegebenen <xref:System.Windows.Controls.Button.OnClick%2A>\-Methode.  
  
 In diesem Beispiel wird eine Schaltfläche mit einem verknüpften <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler zum Abrufen der Textauswahl verwendet.  Wenn der Benutzer auf die Schaltfläche klickt, kopiert die <xref:System.Windows.Controls.Button.OnClick%2A>\-Methode im Textfeld ausgewählten Text in eine Zeichenfolge.  Die besonderen Umstände, unter denen die Textauswahl abgerufen wird \(Klicken auf eine Schaltfläche\), und die mit dieser Auswahl durchgeführte Aktion \(Kopieren der Textauswahl in eine Zeichenfolge\) können problemlos geändert und an eine Vielzahl von Szenarien angepasst werden.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## Beispiel  
 Das folgende [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Beispiel zeigt einen <xref:System.Windows.Controls.Button.OnClick%2A>\-Ereignishandler für die Schaltfläche, die in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für dieses Beispiel definiert wurde.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)