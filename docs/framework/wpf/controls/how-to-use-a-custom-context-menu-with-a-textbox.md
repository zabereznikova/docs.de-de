---
title: "Gewusst wie: Verwenden eines benutzerdefinierten Kontextmen&#252;s mit &quot;TextBox&quot; | Microsoft Docs"
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
  - "Kontextmenüs, Benutzerdefiniert"
  - "Benutzerdefinierte Kontextmenüs"
  - "Menüs, Benutzerdefiniert"
  - "TextBox-Steuerelement, Benutzerdefinierte Inhaltsmenüs"
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden eines benutzerdefinierten Kontextmen&#252;s mit &quot;TextBox&quot;
Dieses Beispiel zeigt, wie Sie für ein <xref:System.Windows.Controls.TextBox>\-Steuerelement ein einfaches benutzerdefiniertes Kontextmenü definieren und implementieren.  
  
## Beispiel  
 Im folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel wird ein <xref:System.Windows.Controls.TextBox>\-Steuerelement definiert, das ein benutzerdefiniertes Kontextmenü enthält.  
  
 Das Kontextmenü wird mithilfe eines <xref:System.Windows.Controls.ContextMenu>\-Elements definiert.  Das Kontextmenü selbst besteht aus einer Reihe von <xref:System.Windows.Controls.MenuItem>\-Elementen und <xref:System.Windows.Controls.Separator>\-Elementen.  Jedes <xref:System.Windows.Controls.MenuItem>\-Element definiert einen Befehl im Kontextmenü. Das <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Attribut definiert den Anzeigetext für den Menübefehl, und das <xref:System.Windows.Controls.MenuItem.Click>\-Attribut gibt für jedes Menüelement eine Handlermethode an.  Das <xref:System.Windows.Controls.Separator>\-Element bewirkt lediglich, dass zwischen dem vorherigen und dem nachfolgenden Menüelement eine Linie eingefügt wird.  
  
 [!code-xml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## Beispiel  
 Das folgende Beispiel zeigt den Implementierungscode für die oben angegebene Kontextmenüdefinition sowie den Code an, der das Kontextmenü aktiviert bzw. deaktiviert.  Das <xref:System.Windows.Controls.ContextMenu.Opened>\-Ereignis wird verwendet, um bestimmte Befehle in Abhängigkeit vom aktuellen Zustand der <xref:System.Windows.Controls.TextBox> dynamisch zu aktivieren bzw. zu deaktivieren.  
  
 Zum Wiederherstellen des standardmäßigen Kontextmenüs verwenden Sie die <xref:System.Windows.DependencyObject.ClearValue%2A>\-Methode, um den Wert der <xref:System.Windows.FrameworkElement.ContextMenu%2A>\-Eigenschaft zu löschen.  Zum vollständigen Deaktivieren des Kontextmenüs setzen Sie die <xref:System.Windows.FrameworkElement.ContextMenu%2A>\-Eigenschaft auf einen NULL\-Verweis \(`Nothing` in Visual Basic\).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## Siehe auch  
 [Verwenden der Rechtschreibprüfung mit einem Kontextmenü](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)