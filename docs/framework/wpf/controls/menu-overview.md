---
title: Übersicht über Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124649"
---
# <a name="menu-overview"></a>Übersicht über Menu
Die <xref:System.Windows.Controls.Menu>-Klasse ermöglicht es Ihnen, Elemente, die Befehlen und Ereignis Handlern zugeordnet sind, in einer hierarchischen Reihenfolge zu organisieren. Jedes <xref:System.Windows.Controls.Menu> Element enthält eine Auflistung von <xref:System.Windows.Controls.MenuItem> Elementen.  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu-Steuerelement  
 Das <xref:System.Windows.Controls.Menu>-Steuerelement stellt eine Liste von Elementen dar, die Befehle oder Optionen für eine Anwendung angeben. Wenn Sie auf eine <xref:System.Windows.Controls.MenuItem> klicken, wird in der Regel ein Untermenü geöffnet, oder eine Anwendung führt einen Befehl aus.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Erstellen von Menüs  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Menu> erstellt, um Text in einem <xref:System.Windows.Controls.TextBox>zu bearbeiten. Die <xref:System.Windows.Controls.Menu> enthält <xref:System.Windows.Controls.MenuItem> Objekte, die die Eigenschaften <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>und <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> sowie die <xref:System.Windows.Controls.MenuItem.Checked>-, <xref:System.Windows.Controls.MenuItem.Unchecked>-und <xref:System.Windows.Controls.MenuItem.Click>-Ereignisse verwenden.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems mit Tastenkombinationen  
 Tastenkombinationen sind Zeichenkombinationen, die mit der Tastatur eingegeben werden können, um <xref:System.Windows.Controls.Menu> Befehle aufzurufen. Die Tastenkombination für **Kopieren** ist beispielsweise STRG+C. Es gibt zwei Eigenschaften, die mit Tastenkombinationen und Menü Elementen –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>verwendet werden können.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.MenuItem.InputGestureText%2A>-Eigenschaft verwendet wird, um <xref:System.Windows.Controls.MenuItem> Steuerelementen Tastenkombinationen zuzuweisen. Dadurch wird nur die Tastenkombination im Menüelement platziert.  Der Befehl wird dem <xref:System.Windows.Controls.MenuItem>nicht zugeordnet. Die Anwendung muss die Eingabe des Benutzers bearbeiten, um die Aktion auszuführen.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Get-Help  
 Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.Command%2A>-Eigenschaft verwenden, um die Befehle " **Öffnen** " und " **Speichern** " <xref:System.Windows.Controls.MenuItem> Steuerelementen zuzuordnen. Die Befehls Eigenschaft ordnet einen Befehl nicht nur einem <xref:System.Windows.Controls.MenuItem>zu, sondern stellt auch den Text der Eingabe Bewegung bereit, der als Verknüpfung verwendet werden soll.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Die <xref:System.Windows.Controls.MenuItem>-Klasse verfügt auch über eine <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>-Eigenschaft, die das Element angibt, in dem der Befehl auftritt. Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt ist, empfängt das Element, das über den Tastaturfokus verfügt, den Befehl. Weitere Informationen zu Befehlen finden Sie unter [Befehlsübersicht](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Menu-Format  
 Mit der Steuerelement Formatierung können Sie die Darstellung und das Verhalten von <xref:System.Windows.Controls.Menu> Steuerelementen drastisch ändern, ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Zusätzlich zum Festlegen von visuellen Eigenschaften können Sie auch eine <xref:System.Windows.Style> auf einzelne Teile eines Steuer Elements anwenden, das Verhalten der Teile des Steuer Elements durch Eigenschaften ändern oder weitere Teile hinzufügen oder das Layout eines Steuer Elements ändern. In den folgenden Beispielen werden verschiedene Möglichkeiten zum Hinzufügen eines <xref:System.Windows.Style> zu einem <xref:System.Windows.Controls.Menu> Steuerelement veranschaulicht.  
  
 Im ersten Codebeispiel wird eine <xref:System.Windows.Style> mit dem Namen `Simple` definiert, die zeigt, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden. Der Code weist die Farbe von `MenuHighlightBrush` als Hintergrundfarbe des Menüs und die Farbe von `MenuTextBrush` als Vordergrundfarbe des Menüs zu. Beachten Sie, dass Sie zum Zuweisen der Pinsel Ressourcenschlüssel verwenden.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Im folgenden Beispiel werden <xref:System.Windows.Trigger> Elemente verwendet, die es Ihnen ermöglichen, die Darstellung einer <xref:System.Windows.Controls.MenuItem> als Reaktion auf Ereignisse zu ändern, die auf dem <xref:System.Windows.Controls.Menu>auftreten. Wenn Sie die Maus über die <xref:System.Windows.Controls.Menu>bewegen, ändern sich die Vordergrundfarbe und die Schriftart Merkmale der Menü Elemente.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
