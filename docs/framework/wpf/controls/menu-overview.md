---
title: Übersicht über Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 4c3e8398ad058c50df535fea88dd9f366b7f24ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="menu-overview"></a>Übersicht über Menu
Die <xref:System.Windows.Controls.Menu> -Klasse ermöglicht es Ihnen, zum Organisieren von Elementen, die Befehlen und Ereignishandlern in einer hierarchischen Reihenfolge zugeordnet. Jede <xref:System.Windows.Controls.Menu> Element enthält eine Auflistung von <xref:System.Windows.Controls.MenuItem> Elemente.  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu-Steuerelement  
 Die <xref:System.Windows.Controls.Menu> Steuerelement stellt eine Liste von Elementen, die Befehle oder Optionen für eine Anwendung angeben. Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> öffnet ein Untermenü oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Erstellen von Menüs  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> zum Bearbeiten von Text in einem <xref:System.Windows.Controls.TextBox>. Die <xref:System.Windows.Controls.Menu> enthält <xref:System.Windows.Controls.MenuItem> Objekten, die <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, und <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaften und die <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, und <xref:System.Windows.Controls.MenuItem.Click> Ereignisse.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems mit Tastenkombinationen  
 Tastenkombinationen sind Zeichenkombinationen, die mit der Tastatur aufzurufenden eingegeben werden können <xref:System.Windows.Controls.Menu> Befehle. Die Tastenkombination für **Kopieren** ist beispielsweise STRG+C. Es gibt zwei Eigenschaften zur Verwendung mit Tastenkombinationen und Menüelemente –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> Eigenschaft zuweisen Tastenkombinationstext <xref:System.Windows.Controls.MenuItem> Steuerelemente. Dadurch wird nur die Tastenkombination im Menüelement platziert.  Es erfolgt keine Zuordnung zwischen den Befehl mit der <xref:System.Windows.Controls.MenuItem>. Die Anwendung muss die Eingabe des Benutzers bearbeiten, um die Aktion auszuführen.  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Befehl  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.Command%2A> zu verknüpfende Eigenschaft der **öffnen** und **speichern** Befehle mit <xref:System.Windows.Controls.MenuItem> Steuerelemente. Nicht nur ist die Befehlseigenschaft ordnen Sie einen Befehl mit einem <xref:System.Windows.Controls.MenuItem>, sondern stellt auch die Eingabeaktion Text, der als Verknüpfung.  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Die <xref:System.Windows.Controls.MenuItem> -Klasse verfügt auch über eine <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> Eigenschaft, die das Element angibt, in dem der Befehl auftritt. Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> ist nicht festgelegt ist, wird der Befehl in das Element, das über den Tastaturfokus verfügt. Weitere Informationen zu Befehlen finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Menu-Format  
 Mit Formatieren von Steuerelementen können Sie deutlich das Aussehen und Verhalten der ändern <xref:System.Windows.Controls.Menu> Steuerelemente ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Sie können auch anwenden, zusätzlich zum Festlegen von Eigenschaften visueller Elemente, eine <xref:System.Windows.Style> für einzelne Teile eines Steuerelements ändern das Verhalten von Teilen des Steuerelements über Eigenschaften, zusätzliche Teile hinzufügen oder Ändern des Layouts eines Steuerelements. Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Hinzufügen einer <xref:System.Windows.Style> zu einem <xref:System.Windows.Controls.Menu> Steuerelement.  
  
 Im erste Codebeispiel definiert eine <xref:System.Windows.Style> aufgerufen `Simple` veranschaulicht, wie die aktuellen Systemeinstellungen in Ihr Format zu verwenden. Der Code weist die Farbe von `MenuHighlightBrush` als Hintergrundfarbe des Menüs und die Farbe von `MenuTextBrush` als Vordergrundfarbe des Menüs zu. Beachten Sie, dass Sie zum Zuweisen der Pinsel Ressourcenschlüssel verwenden.  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Das folgende Beispiel verwendet <xref:System.Windows.Trigger> Elemente, die Ihnen ermöglichen, ändern Sie die Darstellung von einer <xref:System.Windows.Controls.MenuItem> als Antwort auf Ereignisse, die auftreten, auf die <xref:System.Windows.Controls.Menu>. Wenn Sie den Mauszeiger über die <xref:System.Windows.Controls.Menu>, Vordergrundfarbe und Schriftartmerkmale der Menüelemente ändern.  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für WPF-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)
