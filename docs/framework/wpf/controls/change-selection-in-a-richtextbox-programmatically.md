---
title: "Programmgesteuertes &#196;ndern der Auswahl in einem RichTextBox-Element | Microsoft Docs"
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
  - "Ändern der Auswahl in einer RichTextBox [WPF]"
  - "Ändern der Auswahl in einem Textfeld [WPF]"
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Programmgesteuertes &#196;ndern der Auswahl in einem RichTextBox-Element
In diesem Beispiel wird gezeigt, wie die aktuelle Auswahl in einem <xref:System.Windows.Controls.RichTextBox>\-Element programmgesteuert geändert wird.  Die Auswahl ist genau so, als hätte der Benutzer den Inhalt über die Benutzeroberfläche ausgewählt.  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox>\-Steuerelement mit einfachem Inhalt.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## Beispiel  
 Im folgenden Code wird programmgesteuert ein beliebiger Textbereich ausgewählt, wenn der Benutzer in das <xref:System.Windows.Controls.RichTextBox>\-Element klickt.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## Siehe auch  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)