---
title: 'Gewusst wie: Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: edcf6bdf381ae51a3354f9bc0b3c91d86e1f8f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Gewusst wie: Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"
In diesem Beispiel wird gezeigt, wie definieren und Implementieren eines einfachen benutzerdefinierten Kontextmenüs für eine <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel definiert eine <xref:System.Windows.Controls.TextBox> -Steuerelement, ein benutzerdefiniertes Kontextmenü enthält.  
  
 Das Kontextmenü wird definiert, mit einem <xref:System.Windows.Controls.ContextMenu> Element.  Im Kontextmenü den Befehl selbst besteht aus einer Reihe von <xref:System.Windows.Controls.MenuItem> Elemente und <xref:System.Windows.Controls.Separator> Elemente.  Jede <xref:System.Windows.Controls.MenuItem> Element definiert einen Befehl im Kontextmenü; der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Attribut definiert den Anzeigetext für den Menübefehl und die <xref:System.Windows.Controls.MenuItem.Click> Attribut gibt eine Handlermethode für jedes Menüelement an.  Die <xref:System.Windows.Controls.Separator> Element einfach führt dazu, dass eine Trennung Linie zwischen dem vorherigen und dem nachfolgenden Menüelement gerendert werden soll.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Implementierungscode für den vorherigen Kontextmenüdefinition sowie den Code, der aktiviert und deaktiviert das Kontextmenü an.  Die <xref:System.Windows.Controls.ContextMenu.Opened> Ereignis wird verwendet, um dynamisch aktivieren oder deaktivieren bestimmte Befehle abhängig von den aktuellen Status des der <xref:System.Windows.Controls.TextBox>.  
  
 Verwenden Sie zum Wiederherstellen des standardmäßigen Kontextmenüs der <xref:System.Windows.DependencyObject.ClearValue%2A> Methode, um den Wert der Löschen der <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft.  Um das Kontextmenü vollständig zu deaktivieren, legen die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft auf einen null-Verweis (`Nothing` in Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Rechtschreibprüfung mit einem Kontextmenü](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
