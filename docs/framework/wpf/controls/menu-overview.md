---
title: Übersicht über Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186974"
---
# <a name="menu-overview"></a>Übersicht über Menu
Mit <xref:System.Windows.Controls.Menu> der Klasse können Sie Elemente, die Befehlen und Ereignishandlern zugeordnet sind, in einer hierarchischen Reihenfolge organisieren. Jedes <xref:System.Windows.Controls.Menu> Element enthält <xref:System.Windows.Controls.MenuItem> eine Auflistung von Elementen.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Menu-Steuerelement  
 Das <xref:System.Windows.Controls.Menu> Steuerelement stellt eine Liste von Elementen dar, die Befehle oder Optionen für eine Anwendung angeben. In der Regel <xref:System.Windows.Controls.MenuItem> wird durch Klicken auf ein Untermenü ein Untermenü geöffnet oder eine Anwendung veranlasst, einen Befehl auszuführen.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>Erstellen von Menüs  
 Im folgenden Beispiel <xref:System.Windows.Controls.Menu> wird ein <xref:System.Windows.Controls.TextBox>zum Bearbeiten von Text in einer erstellt. Der <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.MenuItem> enthält Objekte, <xref:System.Windows.Controls.MenuItem.Command%2A> <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> die , <xref:System.Windows.Controls.MenuItem.Checked> <xref:System.Windows.Controls.MenuItem.Unchecked>und <xref:System.Windows.Controls.MenuItem.Click> Eigenschaften sowie die , und ereignisse verwenden.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems mit Tastenkombinationen  
 Tastenkombinationen sind Zeichenkombinationen, die mit der <xref:System.Windows.Controls.Menu> Tastatur eingegeben werden können, um Befehle aufzurufen. Die Tastenkombination für **Kopieren** ist beispielsweise STRG+C. Es gibt zwei Eigenschaften, die mit Tastenkombinationen und Menüelementen verwendet werden können –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> wie Sie die <xref:System.Windows.Controls.MenuItem> Eigenschaft verwenden, um Steuerelementen Tastenkombinationstext zuzuweisen. Dadurch wird nur die Tastenkombination im Menüelement platziert.  Der Befehl wird nicht <xref:System.Windows.Controls.MenuItem>mit der zugeordnet. Die Anwendung muss die Eingabe des Benutzers bearbeiten, um die Aktion auszuführen.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Get-Help  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.MenuItem.Command%2A> wie Sie die Eigenschaft <xref:System.Windows.Controls.MenuItem> verwenden, um die Befehle **Öffnen** und **Speichern** Steuerelementen zuzuordnen. Die Befehlseigenschaft verknüpft nicht nur <xref:System.Windows.Controls.MenuItem>einen Befehl mit einem , sondern stellt auch den Eingabegestentext bereit, der als Verknüpfung verwendet werden soll.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Die <xref:System.Windows.Controls.MenuItem> Klasse verfügt <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> auch über eine Eigenschaft, die das Element angibt, in dem der Befehl ausgeführt wird. Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt ist, empfängt das Element mit Tastaturfokus den Befehl. Weitere Informationen zu Befehlen finden Sie unter [Befehlsübersicht](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>Menu-Format  
 Mit dem Steuerelementstyling können Sie das <xref:System.Windows.Controls.Menu> Erscheinungsbild und Verhalten von Steuerelementen drastisch ändern, ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Zusätzlich zum Festlegen visueller Eigenschaften können <xref:System.Windows.Style> Sie auch eine auf einzelne Teile eines Steuerelements anwenden, das Verhalten von Teilen des Steuerelements durch Eigenschaften ändern oder zusätzliche Teile hinzufügen oder das Layout eines Steuerelements ändern. Die folgenden Beispiele veranschaulichen <xref:System.Windows.Style> mehrere <xref:System.Windows.Controls.Menu> Möglichkeiten zum Hinzufügen eines zu einem Steuerelement.  
  
 Im ersten Codebeispiel <xref:System.Windows.Style> wird `Simple` ein Aufruf definiert, der zeigt, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden. Der Code weist die Farbe von `MenuHighlightBrush` als Hintergrundfarbe des Menüs und die Farbe von `MenuTextBrush` als Vordergrundfarbe des Menüs zu. Beachten Sie, dass Sie zum Zuweisen der Pinsel Ressourcenschlüssel verwenden.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Im folgenden <xref:System.Windows.Trigger> Beispiel werden Elemente verwendet, mit <xref:System.Windows.Controls.MenuItem> denen Sie die Darstellung <xref:System.Windows.Controls.Menu>eines als Reaktion auf Ereignisse ändern können, die auf der auftreten. Wenn Sie die Maus <xref:System.Windows.Controls.Menu>über die bewegen, ändern sich die Vordergrundfarbe und die Schrifteigenschaften der Menüelemente.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
