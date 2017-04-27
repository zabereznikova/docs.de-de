---
title: "&#220;bersicht &#252;ber Menu | Microsoft Docs"
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
  - "Menu-Steuerelement"
  - "Menü-Steuerelemente"
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#220;bersicht &#252;ber Menu
Die <xref:System.Windows.Controls.Menu> -Klasse können Sie Befehle und Ereignishandler in einer hierarchischen Reihenfolge zugeordneten Elemente zu organisieren. Jede <xref:System.Windows.Controls.Menu> Element enthält eine Auflistung von <xref:System.Windows.Controls.MenuItem> Elemente.  
  
   
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Menu-Steuerelement  
 Die <xref:System.Windows.Controls.Menu> Steuerelement stellt eine Liste von Elementen, die Befehle oder Optionen für eine Anwendung angeben. Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> ein Untermenü geöffnet oder durch die Anwendung, einen Befehl auszuführen.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Erstellen von Menüs  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> zum Bearbeiten von Text in einem <xref:System.Windows.Controls.TextBox>. Die <xref:System.Windows.Controls.Menu> enthält <xref:System.Windows.Controls.MenuItem> Objekten, die <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, und <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaften und die <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, und <xref:System.Windows.Controls.MenuItem.Click> Ereignisse.  
  
 [!code-xml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems mit Tastenkombinationen  
 Tastenkombinationen sind Zeichenkombinationen, die mit der Tastatur aufzurufenden eingegeben werden können <xref:System.Windows.Controls.Menu> Befehle. Z. B. die Verknüpfung für **Kopie** ist STRG + C. Es gibt zwei Eigenschaften werden mit Tastenkombinationen und Menüelementen verwendet –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> Tastenkombinationstext zuzuweisende Eigenschaft <xref:System.Windows.Controls.MenuItem> Steuerelemente. Dies fügt nur die Tastenkombination im Menüelement.  Es erfolgt keine Zuordnung zwischen den Befehl mit der <xref:System.Windows.Controls.MenuItem>. Die Anwendung muss die Eingabe des Benutzers zum Ausführen der Aktion behandeln.  
  
 [!code-xml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Befehl  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.Command%2A> -Eigenschaft zum Zuordnen der **öffnen** und **speichern** Befehle mit <xref:System.Windows.Controls.MenuItem> Steuerelemente. Nicht nur ist die Command-Eigenschaft verknüpft einen Befehl mit einem <xref:System.Windows.Controls.MenuItem>, sondern stellt auch die Eingabeaktion Text, als Verknüpfung verwendet werden.  
  
 [!code-xml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Die <xref:System.Windows.Controls.MenuItem> -Klasse verfügt auch über eine <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> -Eigenschaft, die das Element angibt, in dem der Befehl auftritt. Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt ist, wird der Befehl in das Element, das über den Tastaturfokus verfügt. Weitere Informationen zu Befehlen finden Sie unter [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Menü-Stil  
 Anhand der Formatierung können Sie erheblich das Aussehen und Verhalten der ändern <xref:System.Windows.Controls.Menu> Steuerelemente ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Anwenden einer <xref:System.Windows.Style> für einzelne Teile eines Steuerelements, das Verhalten von Teilen des Steuerelements anhand von Eigenschaften ändern oder zusätzliche Teile hinzufügen oder ändern Sie das Layout eines Steuerelements. Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Hinzufügen einer <xref:System.Windows.Style> auf eine <xref:System.Windows.Controls.Menu> Steuerelement.  
  
 Im erste Codebeispiel definiert eine <xref:System.Windows.Style> namens `Simple` veranschaulicht, wie die aktuellen Systemeinstellungen im Stil verwendet. Weist der Code die Farbe der `MenuHighlightBrush` als Hintergrundfarbe für das Menü und die `MenuTextBrush` als die Vordergrundfarbe. Beachten Sie, dass Sie die Zuweisung der Pinsel Ressourcenschlüssel verwenden.  
  
 [!code-xml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Das folgende Beispiel verwendet <xref:System.Windows.Trigger> Elemente, die Ihnen ermöglichen, ändern Sie die Darstellung von einer <xref:System.Windows.Controls.MenuItem> als Antwort auf Ereignisse in der <xref:System.Windows.Controls.Menu>. Beim Bewegen der Maus über die <xref:System.Windows.Controls.Menu>, Vordergrundfarbe und Schriftartmerkmale der Menüelemente ändern.  
  
 [!code-xml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für WPF-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)