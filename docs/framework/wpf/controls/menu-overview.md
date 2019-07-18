---
title: Übersicht über Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: a3250cfd3fd651cb4ed3c4fd6975f5b5c89195f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942154"
---
# <a name="menu-overview"></a>Übersicht über Menu
Die <xref:System.Windows.Controls.Menu> Klasse ermöglicht Ihnen, Elemente, die zu Befehlen und Ereignishandlern in einer hierarchischen Reihenfolge zu organisieren. Jede <xref:System.Windows.Controls.Menu> Element enthält eine Auflistung von <xref:System.Windows.Controls.MenuItem> Elemente.  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu-Steuerelement  
 Die <xref:System.Windows.Controls.Menu> Steuerelement stellt eine Liste von Elementen, die Befehle oder Optionen für eine Anwendung angeben. Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> ein Untermenü geöffnet oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Erstellen von Menüs  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> Bearbeiten von Text in einem <xref:System.Windows.Controls.TextBox>. Die <xref:System.Windows.Controls.Menu> enthält <xref:System.Windows.Controls.MenuItem> Objekten, die <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, und <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaften und die <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, und <xref:System.Windows.Controls.MenuItem.Click> Ereignisse.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems mit Tastenkombinationen  
 Tastenkombinationen sind Zeichenkombinationen, die mit der Tastatur aufzurufende eingegeben werden können <xref:System.Windows.Controls.Menu> Befehle. Die Tastenkombination für **Kopieren** ist beispielsweise STRG+C. Es gibt zwei Eigenschaften mit Tastenkombinationen und Menüelementen verwendet –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> Eigenschaft zuweisen Tastenkombinationstext <xref:System.Windows.Controls.MenuItem> Steuerelemente. Dadurch wird nur die Tastenkombination im Menüelement platziert.  Es erfolgt keine Zuordnung zwischen den Befehl mit der <xref:System.Windows.Controls.MenuItem>. Die Anwendung muss die Eingabe des Benutzers bearbeiten, um die Aktion auszuführen.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Befehl  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.MenuItem.Command%2A> -Eigenschaft zum Zuordnen der **öffnen** und **speichern** bei Befehlen mit <xref:System.Windows.Controls.MenuItem> Steuerelemente. Nicht nur ist die Command-Eigenschaft ordnen Sie einen Befehl mit einem <xref:System.Windows.Controls.MenuItem>, sondern stellt auch die Eingabegeste-Text, der als Verknüpfung verwendet.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Die <xref:System.Windows.Controls.MenuItem> -Klasse verfügt auch über eine <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> -Eigenschaft, die das Element gibt an, in dem der Befehl auftritt. Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> ist nicht festgelegt ist, wird der Befehl in das Element, das den Tastaturfokus verfügt. Weitere Informationen zu Befehlen finden Sie unter [Befehlsübersicht](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Menu-Format  
 Dank Steuerelementformats Sie erheblich ändern das Aussehen und Verhalten der <xref:System.Windows.Controls.Menu> Steuerelemente ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Sie können auch anwenden, zusätzlich zur Festlegung von visuellen Eigenschaften eine <xref:System.Windows.Style> für einzelne Teile eines Steuerelements, das Verhalten von Teilen des Steuerelements durch Eigenschaften ändern oder zusätzliche Teile hinzufügen oder ändern Sie das Layout eines Steuerelements. Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Hinzufügen einer <xref:System.Windows.Style> zu einem <xref:System.Windows.Controls.Menu> Steuerelement.  
  
 Im erste Codebeispiel definiert eine <xref:System.Windows.Style> namens `Simple` , die zeigt, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet. Der Code weist die Farbe von `MenuHighlightBrush` als Hintergrundfarbe des Menüs und die Farbe von `MenuTextBrush` als Vordergrundfarbe des Menüs zu. Beachten Sie, dass Sie zum Zuweisen der Pinsel Ressourcenschlüssel verwenden.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Das folgende Beispiel verwendet <xref:System.Windows.Trigger> Elemente, die Sie ändern die Darstellung der ermöglichen eine <xref:System.Windows.Controls.MenuItem> als Reaktion auf Ereignisse in der <xref:System.Windows.Controls.Menu>. Wenn Sie über die Maus bewegen der <xref:System.Windows.Controls.Menu>, der die Vordergrundfarbe und die Schriftart der Menüelemente ändern.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für WPF-Steuerelementsammlungen](https://go.microsoft.com/fwlink/?LinkID=160053)
