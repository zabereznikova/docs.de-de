---
title: 'Vorgehensweise: Verwenden eines benutzerdefinierten Kontextmenüs mit einem TextBox-Objekt'
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
ms.openlocfilehash: b0507c6fa37f0f51f9e12ebe5f908c39c25b50d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699174"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Vorgehensweise: Verwenden eines benutzerdefinierten Kontextmenüs mit einem TextBox-Objekt
Dieses Beispiel zeigt, wie Sie definieren und Implementieren eines einfachen benutzerdefinierten Kontextmenüs für ein <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel definiert eine <xref:System.Windows.Controls.TextBox> -Steuerelement, das ein benutzerdefiniertes Kontextmenü enthält.  
  
 Das Kontextmenü wird definiert, mit einem <xref:System.Windows.Controls.ContextMenu> Element.  Das Kontextmenü selbst besteht aus einer Reihe von <xref:System.Windows.Controls.MenuItem> Elemente und <xref:System.Windows.Controls.Separator> Elemente.  Jede <xref:System.Windows.Controls.MenuItem> Element definiert einen Befehl im Kontextmenü; die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Attribut definiert den Anzeigetext für den Menübefehl, und die <xref:System.Windows.Controls.MenuItem.Click> Attribut gibt an, eine Handlermethode, die für jedes Menüelement im.  Die <xref:System.Windows.Controls.Separator> Element wird einfach eine Trennung Zeile zwischen den Menüelementen der vorherigen und nachfolgenden gerendert werden soll.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Implementierungscode für den vorherigen Kontextmenüdefinition sowie den Code, der aktiviert und im Kontextmenü deaktiviert.  Die <xref:System.Windows.Controls.ContextMenu.Opened> Ereignis wird verwendet, um dynamisch aktivieren oder deaktivieren je nach den aktuellen Status der bestimmten Befehle die <xref:System.Windows.Controls.TextBox>.  
  
 Verwenden Sie zum Wiederherstellen der standardmäßigen Kontextmenü der <xref:System.Windows.DependencyObject.ClearValue%2A> Methode zum Löschen des Werts, der die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft.  Um das Kontextmenü vollständig zu deaktivieren, legen die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft einen null-Verweis (`Nothing` in Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden der Rechtschreibprüfung mit einem Kontextmenü](how-to-use-spell-checking-with-a-context-menu.md)
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
