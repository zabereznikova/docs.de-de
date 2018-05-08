---
title: Befehlsübersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
ms.openlocfilehash: 0d426d8cf174a61c724e97b5e7af5c1428679716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="commanding-overview"></a>Befehlsübersicht
<a name="introduction"></a> Befehle sind ein Eingabemechanismus in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], der Eingabeverarbeitung auf einer höheren Ebene als die Geräteeingabe bereitstellt. Beispiele für Befehle sind die in vielen Programmen enthaltenen Vorgänge **Kopieren**, **Ausschneiden** und **Einfügen**.  
  
 In dieser Übersicht werden die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthaltenen Befehle, die Klassen, die Teil des Befehlsmodells sind, und die Verwendung und Erstellung von Befehlen in Ihren Anwendungen vorgestellt.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Was sind Befehle?](#commands_at_10000_feet)  
  
-   [Beispiel eines einfachen Befehls in WPF](#simple_command)  
  
-   [Vier Hauptkonzepte für WPF-Befehle](#Four_main_Concepts)  
  
-   [Befehlsbibliothek](#Command_Library)  
  
-   [Erstellen von benutzerdefinierten Befehlen](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>Was sind Befehle?  
 Befehle haben mehrere Zwecke. Der erste ist die Trennung der Semantik und des von einem Befehl aufgerufenen Objekts von der Logik, die den Befehl ausführt. Dadurch können mehrere und unterschiedliche Quellen dieselbe Befehlslogik aufrufen, und die Befehlslogik kann für verschiedene Ziele angepasst werden. Die Bearbeitungsvorgänge **Kopieren**, **Ausschneiden** und **Einfügen**, die in vielen Programmen vorkommen, können z.B. mithilfe anderer Benutzeraktionen aufgerufen werden, wenn sie mithilfe von Befehlen implementiert werden. In manchen Anwendungen lassen sich ausgewählte Objekte oder Text durch einen Klick auf eine Schaltfläche, durch Auswählen eines Elements in einem Menü oder über eine Tastenkombination wie STRG+X ausschneiden. Mithilfe von Befehlen können Sie jede Art von Benutzeraktion an die gleiche Logik binden.  
  
 Ein weiterer Zweck von Befehlen ist es, die Verfügbarkeit von Aktionen anzugeben. Setzen wir das vorherige Beispiel fort: Das Ausschneiden eines Objekts oder Texts ist nur sinnvoll, wenn ein Objekt ausgewählt wurde. Wenn ein Benutzer versucht, ein Objekt oder Text auszuschneiden, ohne dass etwas ausgewählt wurde, passiert nichts. Um dies für Benutzer kenntlich zu machen, werden Schaltflächen und Menüelemente in vielen Anwendungen deaktiviert. So weiß der Benutzer, ob es möglich ist, eine Aktion auszuführen. Kann ein Befehl angegeben werden, ob eine Aktion möglich, durch die Implementierung ist der <xref:System.Windows.Input.ICommand.CanExecute%2A> Methode. Eine Schaltfläche abonnieren kann die <xref:System.Windows.Input.ICommand.CanExecuteChanged> Ereignis und deaktiviert werden, wenn <xref:System.Windows.Input.ICommand.CanExecute%2A> gibt `false` oder aktiviert werden, wenn <xref:System.Windows.Input.ICommand.CanExecute%2A> gibt `true`.  
  
 Die Semantik eines Befehls kann anwendungs- und klassenübergreifend konsistent sein. Die Logik einer Aktion ist aber dem betreffenden Objekt eigen, auf das die Aktion ausgeführt wird. Die Tastenkombination STRG+X ruft zwar den Befehl **Ausschneiden** in Textklassen, Bildklassen und Webbrowsern auf, aber die eigentliche Logik für die Ausführung des Vorgangs **Ausschneiden** wird von der Anwendung definiert, die ihn ausführt. Ein <xref:System.Windows.Input.RoutedCommand> ermöglicht es Clients, die Logik implementieren. Ein Textobjekt kann den markierten Text ausschneiden und in die Zwischenablage kopieren, während ein Bildobjekt das markierte Bild ausschneiden kann. Wenn eine Anwendung behandelt den <xref:System.Windows.Input.CommandManager.Executed> Ereignis, er hat Zugriff auf das Ziel des Befehls und dauert je nach Art des Ziels geeignete Maßnahmen.  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>Beispiel eines einfachen Befehls in WPF  
 Die einfachste Möglichkeit, verwenden Sie einen Befehl in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist die Verwendung eines vordefinierten <xref:System.Windows.Input.RoutedCommand> aus der Bibliothek Befehlsklassen; verwenden Sie ein Steuerelement, das systemeigene Unterstützung für die Verarbeitung des Befehls; hat und ein Steuerelement, das systemeigene Unterstützung für das Aufrufen eines Befehls verfügt.  Die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl ist einer der vordefinierten Befehle in der <xref:System.Windows.Input.ApplicationCommands> Klasse.  Die <xref:System.Windows.Controls.TextBox> Steuerelement verfügt über integrierte Logik für die Verarbeitung der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl.  Und die <xref:System.Windows.Controls.MenuItem> -Klasse verfügt über systemeigene Unterstützung für das Aufrufen von Befehlen.  
  
 Im folgende Beispiel wird gezeigt, wie zum Einrichten einer <xref:System.Windows.Controls.MenuItem> , wenn darauf geklickt wird aufgerufen der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl eine <xref:System.Windows.Controls.TextBox>davon ausgegangen, dass die <xref:System.Windows.Controls.TextBox> über den Tastaturfokus verfügt.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>Vier Hauptkonzepte für WPF-Befehle  
 Das Modell der weitergeleiteten Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann auf vier Hauptkonzepte heruntergebrochen werden: der Befehl, die Befehlsquelle, das Ziel des Befehls und die Befehlsbindung:  
  
-   Die *Befehl* ist die Aktion, die ausgeführt werden soll.  
  
-   Die *Befehlsquelle* ist das Objekt, das den Befehl aufruft.  
  
-   Das *Befehlsziel* ist das Objekt, auf das der Befehl ausgeführt wird.  
  
-   Die *Befehlsbindung* ist das Objekt, das den Befehl der Befehlslogik zuordnet.  
  
 Im vorherigen Beispiel der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl wird der Befehl die <xref:System.Windows.Controls.MenuItem> ist die Befehlsquelle der <xref:System.Windows.Controls.TextBox> das Befehlsziel, und die Befehl Bindung bereitgestellt wird durch die <xref:System.Windows.Controls.TextBox> Steuerelement.  Ist anzumerken, dass es nicht immer der Fall ist, die die <xref:System.Windows.Input.CommandBinding> werden durch das Steuerelement, das die Befehlsklasse für Ziel angegeben.  Sehr häufig die <xref:System.Windows.Input.CommandBinding> muss vom Anwendungsentwickler erstellt werden oder die <xref:System.Windows.Input.CommandBinding> an einen Vorgänger des Befehlsziels verbunden sein.  
  
<a name="Commands"></a>   
### <a name="commands"></a>Befehle  
 Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entstehen durch Implementieren der <xref:System.Windows.Input.ICommand> Schnittstelle.  <xref:System.Windows.Input.ICommand> stellt zwei Methoden <xref:System.Windows.Input.ICommand.Execute%2A>, und <xref:System.Windows.Input.ICommand.CanExecute%2A>, und ein Ereignis <xref:System.Windows.Input.ICommand.CanExecuteChanged>. <xref:System.Windows.Input.ICommand.Execute%2A> führt die Aktionen, die dem Befehl zugeordnet sind. <xref:System.Windows.Input.ICommand.CanExecute%2A> Bestimmt, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden kann. <xref:System.Windows.Input.ICommand.CanExecuteChanged> wird ausgelöst, wenn der Befehl-Manager, der die Befehle Vorgänge zentralisiert eine Änderung in die Befehlsquelle erkennt, die einen Befehl, der ausgelöst wurde aber noch nicht ausgeführt werden, indem der Befehl-Bindung für ungültig erklären kann.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung von <xref:System.Windows.Input.ICommand> ist die <xref:System.Windows.Input.RoutedCommand> -Klasse und liegt der Schwerpunkt dieser Übersicht.  
  
 Die Hauptquellen für die Eingabe in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die Maus, Tastatur, Freihandeingaben und weitergeleitete Befehle.  Verwenden Sie die Eingaben mehr Geräte-oriented eine <xref:System.Windows.RoutedEvent> auf Objekte in einer Anwendungsseite zu informieren, die ein Eingabeereignis aufgetreten ist.  Ein <xref:System.Windows.Input.RoutedCommand> unterscheidet sich nicht.  Die <xref:System.Windows.Input.RoutedCommand.Execute%2A> und <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> Methoden eine <xref:System.Windows.Input.RoutedCommand> enthalten nicht die Anwendungslogik für den Befehl, aber stattdessen lösen Routingereignisse dieser Tunnel und durch die Elementstruktur weitergeleitet werden, bis sie feststellen, dass ein Objekt mit einem <xref:System.Windows.Input.CommandBinding>.  Die <xref:System.Windows.Input.CommandBinding> enthält die Handler für diese Ereignisse und stellt die Handler, der den Befehl auszuführen.  Weitere Informationen zum Ereignisrouting in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Die <xref:System.Windows.Input.RoutedCommand.Execute%2A> Methode auf eine <xref:System.Windows.Input.RoutedCommand> löst die <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> Ereignisse für das Befehlsziel.  Die <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> Methode auf eine <xref:System.Windows.Input.RoutedCommand> löst die <xref:System.Windows.Input.CommandManager.CanExecute> und <xref:System.Windows.Input.CommandManager.PreviewCanExecute> Ereignisse für das Befehlsziel.  Diese Ereignisse und aufwärts durch die Elementstruktur, bis sie ein Objekt auftreten besitzt eine <xref:System.Windows.Input.CommandBinding> für diesen bestimmten Befehl.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt ein Satz von gängigen weitergeleiteten Befehlen, die auf mehrere Klassen verteilt: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, und <xref:System.Windows.Documents.EditingCommands>.  Diese Klassen umfassen nur die <xref:System.Windows.Input.RoutedCommand> Objekte und nicht auf die Implementierungslogik des Befehls.  Die Implementierungslogik ist die Verantwortung des Objekts, für das der Befehl ausgeführt wird.  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>Befehlsquellen  
 Eine Befehlsquelle ist das Objekt, das den Befehl aufruft.  Beispiele für Befehlsquellen sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Input.KeyGesture>.  
  
 Quellen im Befehl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in der Regel implementieren Sie die <xref:System.Windows.Input.ICommandSource> Schnittstelle.  
  
 <xref:System.Windows.Input.ICommandSource> macht drei Eigenschaften verfügbar: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, und <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> ist der Befehl ausgeführt wird, wenn die Befehlsquelle aufgerufen wird.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt auf dem der Befehl ausgeführt werden.  Es ist zu beachten, dass in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> Eigenschaft auf <xref:System.Windows.Input.ICommandSource> ist nur anwendbar, wenn die <xref:System.Windows.Input.ICommand> ist eine <xref:System.Windows.Input.RoutedCommand>.  Wenn die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> festgelegt ist, auf ein <xref:System.Windows.Input.ICommandSource> und der entsprechende Befehl ist kein <xref:System.Windows.Input.RoutedCommand>, das Befehlsziel wird ignoriert. Wenn die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist nicht festgelegt ist, wird das Element mit dem Tastaturfokus wird das Befehlsziel sein.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ein benutzerdefinierten Datentyp verwendet, um Informationen an die Handler zu übergeben, der den Befehl implementieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen implementiert, <xref:System.Windows.Input.ICommandSource> sind <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink>, und <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, und <xref:System.Windows.Documents.Hyperlink> rufen Sie einen Befehl aus, wenn darauf geklickt wird, und ein <xref:System.Windows.Input.InputBinding> Ruft einen Befehl bei der <xref:System.Windows.Input.InputGesture> verknüpft sind mit ausgeführt wird.  
  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.MenuItem> in einer <xref:System.Windows.Controls.ContextMenu> als Befehlsquelle für einen für die <xref:System.Windows.Input.ApplicationCommands.Properties%2A> Befehl.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 In der Regel eine Befehlsquelle überwacht die <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> Ereignis.  Dieses Ereignis teilt der Befehlsquelle mit, dass sich die Fähigkeit des Befehls zur Ausführung für das aktuelle Befehlsziel möglicherweise geändert hat.  Die Befehlsquelle kann den aktuellen Status der Abfrage der <xref:System.Windows.Input.RoutedCommand> mithilfe der <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> Methode.  Befehlsquelle sich kann dann selbst deaktivieren, wenn der Befehl nicht ausgeführt werden kann.  Ein Beispiel hierfür ist eine <xref:System.Windows.Controls.MenuItem> ausgrauen, dass selbst wenn ein Befehl nicht ausführen kann.  
  
 Ein <xref:System.Windows.Input.InputGesture> als Befehlsquelle verwendet werden können.  Zwei Typen von Eingabeaktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die <xref:System.Windows.Input.KeyGesture> und <xref:System.Windows.Input.MouseGesture>.  Sie können sich vorstellen eine <xref:System.Windows.Input.KeyGesture> als eine Tastenkombination, z. B. STRG + C.  Ein <xref:System.Windows.Input.KeyGesture> besteht aus einem <xref:System.Windows.Input.Key> und einen Satz von <xref:System.Windows.Input.ModifierKeys>.  Ein <xref:System.Windows.Input.MouseGesture> besteht aus einem <xref:System.Windows.Input.MouseAction> und einen optionalen Satz <xref:System.Windows.Input.ModifierKeys>.  
  
 In der Reihenfolge für eine <xref:System.Windows.Input.InputGesture> als Befehlsquelle fungieren zu können, muss er mit einem Befehl zugeordnet sein. Hierzu gibt es zwei Möglichkeiten.  Eine Möglichkeit ist die Verwendung einer <xref:System.Windows.Input.InputBinding>.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Input.KeyBinding> zwischen einem <xref:System.Windows.Input.KeyGesture> und ein <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Eine weitere Möglichkeit zum Zuordnen einer <xref:System.Windows.Input.InputGesture> auf eine <xref:System.Windows.Input.RoutedCommand> besteht im Hinzufügen der <xref:System.Windows.Input.InputGesture> zu der <xref:System.Windows.Input.InputGestureCollection> auf der <xref:System.Windows.Input.RoutedCommand>.  
  
 Das folgende Beispiel veranschaulicht das Hinzufügen einer <xref:System.Windows.Input.KeyGesture> auf die <xref:System.Windows.Input.InputGestureCollection> des eine <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 Ein <xref:System.Windows.Input.CommandBinding> ordnet einem Befehl die Ereignishandler, die den Befehl zu implementieren.  
  
 Die <xref:System.Windows.Input.CommandBinding> Klasse enthält eine <xref:System.Windows.Input.CommandBinding.Command%2A> -Eigenschaft, und <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>, und <xref:System.Windows.Input.CommandBinding.CanExecute> Ereignisse.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> ist der Befehl, der <xref:System.Windows.Input.CommandBinding> zugeordnet wird.  Die Ereignishandler, die angefügt sind die <xref:System.Windows.Input.CommandBinding.PreviewExecuted> und <xref:System.Windows.Input.CommandBinding.Executed> Ereignisse implementieren die Befehlslogik.  Der Ereignishandler angefügt wird, um die <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> und <xref:System.Windows.Input.CommandBinding.CanExecute> Ereignisse zu bestimmen, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden kann.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Input.CommandBinding> im Stamm <xref:System.Windows.Window> einer Anwendung.  Die <xref:System.Windows.Input.CommandBinding> ordnet die <xref:System.Windows.Input.ApplicationCommands.Open%2A> mit <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> Handler.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Als Nächstes wird die <xref:System.Windows.Input.ExecutedRoutedEventHandler> und eine <xref:System.Windows.Input.CanExecuteRoutedEventHandler> erstellt werden.  Die <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet eine <xref:System.Windows.MessageBox> , anzeigt, dass eine Zeichenfolge, die besagt, der Befehl ausgeführt wurde.  Die <xref:System.Windows.Input.CanExecuteRoutedEventHandler> legt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> Eigenschaft `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Ein <xref:System.Windows.Input.CommandBinding> angefügt ist, auf ein bestimmtes Objekt, z. B. im Stammverzeichnis <xref:System.Windows.Window> der Anwendung oder ein Steuerelement.  Das Objekt, das die <xref:System.Windows.Input.CommandBinding> angefügt ist, definiert den Bereich der Bindung.  Z. B. eine <xref:System.Windows.Input.CommandBinding> angefügt an einen Vorgänger des Befehls Ziel erreicht werden kann, indem Sie die <xref:System.Windows.Input.CommandBinding.Executed> Ereignis, aber ein <xref:System.Windows.Input.CommandBinding> angefügt, ein Nachfolger des Befehls Ziel nicht erreichbar.  Dies ist eine direkte Folge der Art und Weise, einen <xref:System.Windows.RoutedEvent> Tunnel und Blasen aus dem Objekt, das das Ereignis auslöst.  
  
 In einigen Situationen die <xref:System.Windows.Input.CommandBinding> wird an das Befehlsziel selbst angefügt, z. B. mit der <xref:System.Windows.Controls.TextBox> Klasse und die <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, und <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehle. Häufig ist es einfacher, fügen Sie der <xref:System.Windows.Input.CommandBinding> an einen Vorgänger des Ziels Befehl wie den Hauptknoten <xref:System.Windows.Window> oder des Application-Objekts, insbesondere dann, wenn identisch <xref:System.Windows.Input.CommandBinding> für mehrere Befehlsziele verwendet werden kann.  Bei Erstellung Ihrer Befehlsinfrastruktur sollten Sie einige Entwurfsentscheidungen in beachten.  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>Befehlsziel  
 Das Befehlsziel ist das Element, für das der Befehl ausgeführt wird.  Bei einem <xref:System.Windows.Input.RoutedCommand>, das Befehlsziel ist das Element, an dem das routing von der <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandManager.CanExecute> gestartet wird.  Wie bereits erwähnt, die zuvor in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> Eigenschaft <xref:System.Windows.Input.ICommandSource> ist nur anwendbar, wenn die <xref:System.Windows.Input.ICommand> ist eine <xref:System.Windows.Input.RoutedCommand>.  Wenn die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> festgelegt ist, auf ein <xref:System.Windows.Input.ICommandSource> und der entsprechende Befehl ist kein <xref:System.Windows.Input.RoutedCommand>, das Befehlsziel wird ignoriert.  
  
 Die Befehlsquelle kann das Befehlsziel explizit festlegen.  Wenn das Befehlsziel nicht definiert ist, wird das Element mit dem Tastaturfokus als Befehlsziel verwendet.  Einer der Vorteile daran, das Elements mit dem Tastaturfokus als Befehlsziel zu verwenden, ist die Tatsache, dass dies dem Anwendungsentwickler erlaubt, dieselbe Befehlsquelle zu verwenden, um einen Befehl für mehrere Ziele aufzurufen, ohne das Befehlsziel nachverfolgen zu müssen.  Z. B. wenn eine <xref:System.Windows.Controls.MenuItem> ruft der **einfügen** -Befehl in einer Anwendung mit einer <xref:System.Windows.Controls.TextBox> Steuerelement und ein <xref:System.Windows.Controls.PasswordBox> -Steuerelement, das Ziel kann entweder der <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.PasswordBox> je nachdem, welche Steuerelement den Tastaturfokus.  
  
 Im folgenden Beispiel wird das explizite Festlegen des Befehlsziels in Markup und der CodeBehind-Datei veranschaulicht.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>Der CommandManager  
 Die <xref:System.Windows.Input.CommandManager> fungiert eine Reihe von Befehl verwandte Funktionen verweisen.  Es stellt einen Satz statischer Methoden zum Hinzufügen und Entfernen von <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute>, und <xref:System.Windows.Input.CommandManager.CanExecute> Ereignishandler verschiedene andere und aus einem bestimmten Element.  DSC bietet eine Möglichkeit zum Registrieren <xref:System.Windows.Input.CommandBinding> und <xref:System.Windows.Input.InputBinding> Objekte auf einer bestimmten Klasse.  Die <xref:System.Windows.Input.CommandManager> bietet auch eine Möglichkeit, über die <xref:System.Windows.Input.CommandManager.RequerySuggested> Ereignis, um einen Befehl zu benachrichtigen, wenn er auslösen soll die <xref:System.Windows.Input.ICommand.CanExecuteChanged> Ereignis.  
  
 Die <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> Methode erzwingt die <xref:System.Windows.Input.CommandManager> zum Auslösen der <xref:System.Windows.Input.CommandManager.RequerySuggested> Ereignis.  Dies ist nützlich für Bedingungen, die von deaktivieren/aktivieren ein Befehls sind jedoch keine Bedingungen, die die <xref:System.Windows.Input.CommandManager> erkennt.  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>Befehlsbibliothek  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vordefinierten Befehlen bereit.  Die Befehlsbibliothek besteht aus den folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>, und die <xref:System.Windows.Input.ComponentCommands>.  Diese Klassen bieten Befehle wie z. B. <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> und <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, und <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Viele dieser Befehle enthalten einen Satz von Standardeingabebindungen.  Wenn Sie z. B. angeben, dass Ihre Anwendung den Kopierbefehl verarbeitet, erhalten Sie automatisch die Tastaturbindung STRG+C. Sie erhalten ebenso Bindungen für andere Eingabegeräte, z.B. Stift-Gesten für [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)]s und Sprachinformationen.  
  
 Wenn Sie in den verschiedenen Bibliotheken mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf Befehle verweisen, können Sie normalerweise den Klassennamen der Bibliotheksklasse weglassen, die die statische Befehlseigenschaft verfügbar macht. In der Regel sind die Befehlsnamen als Zeichenfolgen eindeutig, und die besitzenden Typen sind vorhanden, um eine logische Gruppierung der Befehle bereitzustellen. Zur Mehrdeutigkeitsvermeidung sind sie nicht erforderlich. Sie können z.B. `Command="Cut"` anstelle des ausführlicheren `Command="ApplicationCommands.Cut"` angeben. Dies ist eine benutzerfreundliche-Mechanismus, der in integrierten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor für Befehle (genauer gesagt, es ist ein Verhalten des Typkonverters <xref:System.Windows.Input.ICommand>, welche die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Verweise zur Ladezeit).  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>Erstellen von benutzerdefinierten Befehlen  
 Wenn die Befehle in den Klassen der Befehlsbibliothek nicht Ihren Bedürfnissen entsprechen, können Sie eigene Befehle erstellen.  Sie können auf zwei Arten und Weisen einen benutzerdefinierten Befehl erstellen.  Der erste Schritt besteht von Grund auf neu starten, und Implementieren der <xref:System.Windows.Input.ICommand> Schnittstelle.  Die andere Möglichkeit besteht, und der gängigerer Ansatz ist die Erstellung einer <xref:System.Windows.Input.RoutedCommand> oder ein <xref:System.Windows.Input.RoutedUICommand>.  
  
 Ein Beispiel für das Erstellen einer benutzerdefinierten <xref:System.Windows.Input.RoutedCommand>, finden Sie unter [erstellen Sie eine benutzerdefinierte RoutedCommand Beispiel](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Implementieren von ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [How to: Add a Command to a MenuItem (Vorgehensweise: Hinzufügen eines Befehls zu einem MenuItem)](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)  
 [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](http://go.microsoft.com/fwlink/?LinkID=159980)
