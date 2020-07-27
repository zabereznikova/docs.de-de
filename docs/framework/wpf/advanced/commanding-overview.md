---
title: Befehlsübersicht
description: Erfahren Sie mehr über die Befehls Methode, einen Eingabe Mechanismus in Windows Presentation Foundation, der die Eingabe Verarbeitung auf einer stärker semantischen Ebene als die Geräte Eingabe ermöglicht.
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
ms.openlocfilehash: 4f7d12fbf0de9b1546f15061ab7eb1318378bbbb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168129"
---
# <a name="commanding-overview"></a>Befehlsübersicht
<a name="introduction"></a> Befehle sind ein Eingabemechanismus in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], der Eingabeverarbeitung auf einer höheren Ebene als die Geräteeingabe bereitstellt. Beispiele für Befehle sind die in vielen Programmen enthaltenen Vorgänge **Kopieren**, **Ausschneiden** und **Einfügen**.  
  
 In dieser Übersicht werden die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthaltenen Befehle, die Klassen, die Teil des Befehlsmodells sind, und die Verwendung und Erstellung von Befehlen in Ihren Anwendungen vorgestellt.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Was sind Befehle?](#commands_at_10000_feet)  
  
- [Beispiel eines einfachen Befehls in WPF](#simple_command)  
  
- [Vier Hauptkonzepte für WPF-Befehle](#Four_main_Concepts)  
  
- [Befehlsbibliothek](#Command_Library)  
  
- [Erstellen von benutzerdefinierten Befehlen](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>
## <a name="what-are-commands"></a>Was sind Befehle?  
 Befehle haben mehrere Zwecke. Der erste ist die Trennung der Semantik und des von einem Befehl aufgerufenen Objekts von der Logik, die den Befehl ausführt. Dadurch können mehrere und unterschiedliche Quellen dieselbe Befehlslogik aufrufen, und die Befehlslogik kann für verschiedene Ziele angepasst werden. Die Bearbeitungsvorgänge **Kopieren**, **Ausschneiden** und **Einfügen**, die in vielen Programmen vorkommen, können z.B. mithilfe anderer Benutzeraktionen aufgerufen werden, wenn sie mithilfe von Befehlen implementiert werden. In manchen Anwendungen lassen sich ausgewählte Objekte oder Text durch einen Klick auf eine Schaltfläche, durch Auswählen eines Elements in einem Menü oder über eine Tastenkombination wie STRG+X ausschneiden. Mithilfe von Befehlen können Sie jede Art von Benutzeraktion an die gleiche Logik binden.  
  
 Ein weiterer Zweck von Befehlen ist es, die Verfügbarkeit von Aktionen anzugeben. Setzen wir das vorherige Beispiel fort: Das Ausschneiden eines Objekts oder Texts ist nur sinnvoll, wenn ein Objekt ausgewählt wurde. Wenn ein Benutzer versucht, ein Objekt oder Text auszuschneiden, ohne dass etwas ausgewählt wurde, passiert nichts. Um dies für Benutzer kenntlich zu machen, werden Schaltflächen und Menüelemente in vielen Anwendungen deaktiviert. So weiß der Benutzer, ob es möglich ist, eine Aktion auszuführen. Ein Befehl kann durch Implementierung der Methode <xref:System.Windows.Input.ICommand.CanExecute%2A> angegeben, ob eine Aktion möglich ist. Eine Schaltfläche kann das Ereignis <xref:System.Windows.Input.ICommand.CanExecuteChanged> abonnieren und deaktiviert werden, wenn <xref:System.Windows.Input.ICommand.CanExecute%2A> den Wert `false` zurückgibt, oder aktiviert werden, wenn <xref:System.Windows.Input.ICommand.CanExecute%2A> den Wert `true` zurückgibt.  
  
 Die Semantik eines Befehls kann anwendungs- und klassenübergreifend konsistent sein. Die Logik einer Aktion ist aber dem betreffenden Objekt eigen, auf das die Aktion ausgeführt wird. Die Tastenkombination STRG+X ruft zwar den Befehl **Ausschneiden** in Textklassen, Bildklassen und Webbrowsern auf, aber die eigentliche Logik für die Ausführung des Vorgangs **Ausschneiden** wird von der Anwendung definiert, die ihn ausführt. <xref:System.Windows.Input.RoutedCommand> aktiviert Clients, um die Logik zu implementieren. Ein Textobjekt kann den markierten Text ausschneiden und in die Zwischenablage kopieren, während ein Bildobjekt das markierte Bild ausschneiden kann. Wenn eine Anwendung das Ereignis <xref:System.Windows.Input.CommandManager.Executed> verarbeitet, kann sie auf das Ziel des Befehls zugreifen und je nach Zielart geeignete Maßnahmen ergreifen.  
  
<a name="simple_command"></a>
## <a name="simple-command-example-in-wpf"></a>Beispiel eines einfachen Befehls in WPF  
 Die einfachste Möglichkeit, einen Befehl in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verwenden, ist die Verwendung eines vordefinierten <xref:System.Windows.Input.RoutedCommand>-Befehls aus einer der Klassen der Befehlsbibliothek. Verwenden Sie ein Steuerelement mit nativer Unterstützung für die Verarbeitung des Befehls und eines mit nativer Unterstützung zum Aufrufen eines Befehls.  Der Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> ist einer der vordefinierten Befehle in der Klasse <xref:System.Windows.Input.ApplicationCommands>.  Das Steuerelement <xref:System.Windows.Controls.TextBox> verfügt über integrierte Logik zum Verarbeiten des Befehls <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  Und die Klasse <xref:System.Windows.Controls.MenuItem> verfügt über native Unterstützung für das Aufrufen von Befehlen.  
  
 Im folgenden Beispiel wird dargestellt, wie <xref:System.Windows.Controls.MenuItem> eingerichtet wird, damit der Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> auf <xref:System.Windows.Controls.TextBox> mit der Annahme, dass <xref:System.Windows.Controls.TextBox> über den Tastaturfokus verfügt, aufgerufen wird, wenn darauf geklickt wird.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>
## <a name="four-main-concepts-in-wpf-commanding"></a>Vier Hauptkonzepte für WPF-Befehle  
 Das Modell der weitergeleiteten Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann auf vier Hauptkonzepte heruntergebrochen werden: der Befehl, die Befehlsquelle, das Ziel des Befehls und die Befehlsbindung:  
  
- Die *Befehl* ist die Aktion, die ausgeführt werden soll.  
  
- Die *Befehlsquelle* ist das Objekt, das den Befehl aufruft.  
  
- Das *Befehlsziel* ist das Objekt, auf das der Befehl ausgeführt wird.  
  
- Die *Befehlsbindung* ist das Objekt, das den Befehl der Befehlslogik zuordnet.  
  
 Im vorherigen Beispiel ist <xref:System.Windows.Input.ApplicationCommands.Paste%2A> der Befehl, <xref:System.Windows.Controls.MenuItem> die Befehlsquelle, <xref:System.Windows.Controls.TextBox> das Befehlsziel und die Befehlsbindung wird vom Steuerelement <xref:System.Windows.Controls.TextBox> bereitgestellt.  Beachten Sie, dass <xref:System.Windows.Input.CommandBinding> nicht immer vom Steuerelement angegeben wird, das die Befehlszielklasse darstellt.  <xref:System.Windows.Input.CommandBinding> muss oft vom Anwendungsentwickler erstellt werden, sonst kann es vorkommen, dass <xref:System.Windows.Input.CommandBinding> mit einem Vorgänger des Befehlsziels verbunden ist.  
  
<a name="Commands"></a>
### <a name="commands"></a>Befehle  
 Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden durch Implementieren der <xref:System.Windows.Input.ICommand>-Schnittstelle erstellt.  <xref:System.Windows.Input.ICommand> stellt die zwei Methoden <xref:System.Windows.Input.ICommand.Execute%2A> und <xref:System.Windows.Input.ICommand.CanExecute%2A> sowie ein <xref:System.Windows.Input.ICommand.CanExecuteChanged>-Ereignis zur Verfügung. <xref:System.Windows.Input.ICommand.Execute%2A> führt die Aktionen durch, die dem Befehl zugeordnet sind. <xref:System.Windows.Input.ICommand.CanExecute%2A> bestimmt, ob der Befehl auf dem aktuellen Befehlsziel ausgeführt werden kann. <xref:System.Windows.Input.ICommand.CanExecuteChanged> wird ausgelöst, wenn der Befehls-Manager, der die Befehlsvorgänge zentralisiert, eine Änderung in der Befehlsquelle erkennt, die einen durch die Befehlsbindung ausgelösten Befehl, der noch nicht ausgeführt wurde, für ungültig erklären kann.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung von <xref:System.Windows.Input.ICommand> ist die Klasse <xref:System.Windows.Input.RoutedCommand> und der Schwerpunkt dieser Übersicht.  
  
 Die Hauptquellen für die Eingabe in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die Maus, Tastatur, Freihandeingaben und weitergeleitete Befehle.  Stärker geräteorientierte Eingaben verwenden ein <xref:System.Windows.RoutedEvent>-Objekt, um Objekte auf einer Anwendungsseite darüber zu benachrichtigen, das ein Eingabeereignis aufgetreten ist.  Für <xref:System.Windows.Input.RoutedCommand> besteht kein Unterschied.  Die Methoden <xref:System.Windows.Input.RoutedCommand.Execute%2A> und <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> von <xref:System.Windows.Input.RoutedCommand> enthalten keine Anwendungslogik für den Befehl, stattdessen lösen sie Routingereignisse aus, die durch die Elementstruktur tunneln und bubblen, bis sie ein Objekt mit <xref:System.Windows.Input.CommandBinding> finden.  <xref:System.Windows.Input.CommandBinding> enthält die Handler für diese Ereignisse, und die Handler führen den Befehl aus.  Weitere Informationen zum Ereignisrouting in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 Die Methode <xref:System.Windows.Input.RoutedCommand.Execute%2A> auf <xref:System.Windows.Input.RoutedCommand> löst die Ereignisse <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> auf dem Befehlsziel aus.  Die Methode <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> auf <xref:System.Windows.Input.RoutedCommand> löst die Ereignisse <xref:System.Windows.Input.CommandManager.CanExecute> und <xref:System.Windows.Input.CommandManager.PreviewCanExecute> auf dem Befehlsziel aus.  Diese Ereignisse tunneln und bubblen in der Elementstruktur, bis sie ein Objekt finden, das <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl ausweist.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von häufig verwendeten Befehlen bereit, die auf mehrere Klassen verteilt sind: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> und <xref:System.Windows.Documents.EditingCommands>.  Diese Klassen umfassen nur <xref:System.Windows.Input.RoutedCommand>-Objekte und nicht die Implementierungslogik des Befehls.  Die Implementierungslogik ist die Verantwortung des Objekts, für das der Befehl ausgeführt wird.  
  
<a name="Command_Sources"></a>
### <a name="command-sources"></a>Befehlsquellen  
 Eine Befehlsquelle ist das Objekt, das den Befehl aufruft.  <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Input.KeyGesture> sind Beispiele für Befehlsquellen.  
  
 Befehlsquellen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementieren in der Regel die Schnittstelle <xref:System.Windows.Input.ICommandSource>.  
  
 <xref:System.Windows.Input.ICommandSource> stellt drei Eigenschaften zur Verfügung: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> und <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
- <xref:System.Windows.Input.ICommandSource.Command%2A> ist der Befehl, der ausgeführt wird, wenn die Befehlsquelle aufgerufen wird.  
  
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt, auf dem der Befehl ausgeführt wird.  Beachten Sie, dass die Eigenschaft <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nur auf <xref:System.Windows.Input.ICommandSource> anwendbar ist, wenn <xref:System.Windows.Input.ICommand> ein <xref:System.Windows.Input.RoutedCommand> ist.  Wenn <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> auf eine <xref:System.Windows.Input.ICommandSource> festgelegt und der entsprechende Befehl kein <xref:System.Windows.Input.RoutedCommand> ist, wird das Befehlsziel ignoriert. Wenn <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> nicht festgelegt ist, wird das Element mit dem Tastaturfokus das Befehlsziel sein.  
  
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ist ein benutzerdefinierter Datentyp zum Übergeben von Informationen an die Handler, die den Befehl implementieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen, die <xref:System.Windows.Input.ICommandSource> implementieren, sind <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> und <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> und <xref:System.Windows.Documents.Hyperlink> rufen einen Befehl auf, wenn auf sie geklickt wird, und <xref:System.Windows.Input.InputBinding> ruft einen Befehl auf, wenn das zugeordnete <xref:System.Windows.Input.InputGesture> ausgeführt wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Controls.MenuItem> in <xref:System.Windows.Controls.ContextMenu> als Befehlsquelle für den Befehl <xref:System.Windows.Input.ApplicationCommands.Properties%2A> verwendet wird.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 In der Regel überwacht eine Befehlsquelle das Ereignis <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>.  Dieses Ereignis teilt der Befehlsquelle mit, dass sich die Fähigkeit des Befehls zur Ausführung für das aktuelle Befehlsziel möglicherweise geändert hat.  Die Befehlsquelle kann mithilfe der Methode <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> den aktuellen Status von <xref:System.Windows.Input.RoutedCommand> abfragen.  Befehlsquelle sich kann dann selbst deaktivieren, wenn der Befehl nicht ausgeführt werden kann.  Ein Beispiel hierfür ist ein ausgegrautes <xref:System.Windows.Controls.MenuItem>, wenn ein Befehl nicht ausgeführt werden kann.  
  
 <xref:System.Windows.Input.InputGesture> kann als Befehlsquelle verwendet werden.  <xref:System.Windows.Input.KeyGesture> und <xref:System.Windows.Input.MouseGesture> sind zwei Arten von Eingabegesten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sie können sich <xref:System.Windows.Input.KeyGesture> wie eine Tastenkombination vorstellen, z.B. STRG+C.  <xref:System.Windows.Input.KeyGesture> besteht aus einem <xref:System.Windows.Input.Key> und einer Reihe von <xref:System.Windows.Input.ModifierKeys>.  <xref:System.Windows.Input.MouseGesture> besteht aus einem <xref:System.Windows.Input.MouseAction> und einer optionalen Reihe von <xref:System.Windows.Input.ModifierKeys>.  
  
 Damit <xref:System.Windows.Input.InputGesture> sich wie eine Befehlsquelle verhält, muss es einem Befehl zugeordnet werden. Hierzu gibt es zwei Möglichkeiten.  Eine Möglichkeit ist die Verwendung von <xref:System.Windows.Input.InputBinding>.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Input.KeyBinding> zwischen <xref:System.Windows.Input.KeyGesture> und <xref:System.Windows.Input.RoutedCommand> erstellt wird.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Eine weitere Möglichkeit, um <xref:System.Windows.Input.InputGesture> einem <xref:System.Windows.Input.RoutedCommand> zuzuordnen, besteht darin, <xref:System.Windows.Input.InputGesture> dem <xref:System.Windows.Input.InputGestureCollection> auf <xref:System.Windows.Input.RoutedCommand> hinzuzufügen.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Input.KeyGesture> der <xref:System.Windows.Input.InputGestureCollection> von <xref:System.Windows.Input.RoutedCommand> hinzugefügt wird.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>
### <a name="commandbinding"></a>CommandBinding  
 <xref:System.Windows.Input.CommandBinding> ordnet ein Befehl den Ereignishandlern zu, die den Befehl implementieren.  
  
 Die Klasse <xref:System.Windows.Input.CommandBinding> enthält eine <xref:System.Windows.Input.CommandBinding.Command%2A>-Eigenschaft und die Ereignisse <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> und <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> ist der Befehl, dem <xref:System.Windows.Input.CommandBinding> zugeordnet wird.  Die Ereignishandler, die den Ereignissen <xref:System.Windows.Input.CommandBinding.PreviewExecuted> und <xref:System.Windows.Input.CommandBinding.Executed> zugeordnet sind, implementieren die Befehlslogik.  Die Ereignishandler, die den Ereignissen <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> und <xref:System.Windows.Input.CommandBinding.CanExecute> zugeordnet sind, bestimmen, ob der Befehl auf dem aktuellen Befehlsziel ausgeführt werden kann.  
  
 Das folgende Beispiel veranschaulicht das Erstellen von <xref:System.Windows.Input.CommandBinding> auf dem <xref:System.Windows.Window>-Stamm einer Anwendung.  <xref:System.Windows.Input.CommandBinding> ordnet den Befehl <xref:System.Windows.Input.ApplicationCommands.Open%2A> den Handlern <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> zu.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Als Nächstes werden die <xref:System.Windows.Input.ExecutedRoutedEventHandler>- und <xref:System.Windows.Input.CanExecuteRoutedEventHandler>-Objekte erstellt.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet eine <xref:System.Windows.MessageBox>-Klasse, die eine Zeichenfolge anzeigt, die angibt, dass der Befehl ausgeführt wurde.  Der <xref:System.Windows.Input.CanExecuteRoutedEventHandler> legt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>-Eigenschaft auf `true` fest.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 <xref:System.Windows.Input.CommandBinding> wird einem spezifischen Objekt zugeordnet, z.B. dem <xref:System.Windows.Window>-Stamm der Anwendung oder eines Steuerelements.  Das Objekt, dem <xref:System.Windows.Input.CommandBinding> zugeordnet ist, definiert den Bereich der Bindung.  Einem Vorgänger des Befehlsziels zugeordnete <xref:System.Windows.Input.CommandBinding> kann beispielsweise mit dem Ereignis <xref:System.Windows.Input.CommandBinding.Executed> erreicht werden, jedoch kann eine <xref:System.Windows.Input.CommandBinding>, die einem Nachfolger des Befehlsziels zugeordnet ist, nicht erreicht werden.  Dies ist eine direkte Folge der Art und Weise, wie <xref:System.Windows.RoutedEvent> vom Objekt in der Hierarchie ab- und aufsteigt (tunneln und bubbeln), das das Ereignis auslöst.  
  
 In manchen Situationen wird <xref:System.Windows.Input.CommandBinding> dem Befehlsziel selbst zugeordnet, z.B. bei der Klasse <xref:System.Windows.Controls.TextBox> und den Befehlen <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> und <xref:System.Windows.Input.ApplicationCommands.Paste%2A>. In vielen Fällen ist er einfacher, <xref:System.Windows.Input.CommandBinding> dem Vorgänger des Befehlsziels zuzuordnen, z.B. der <xref:System.Windows.Window>-Hauptklasse oder dem Anwendungsobjekt, insbesondere wenn dieselbe <xref:System.Windows.Input.CommandBinding> für mehrere Befehlsziele verwendet werden kann.  Bei Erstellung Ihrer Befehlsinfrastruktur sollten Sie einige Entwurfsentscheidungen in beachten.  
  
<a name="Commane_Target"></a>
### <a name="command-target"></a>Befehlsziel  
 Das Befehlsziel ist das Element, für das der Befehl ausgeführt wird.  Bei <xref:System.Windows.Input.RoutedCommand> ist das Befehlsziel das Element, bei dem das Routing von <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandManager.CanExecute> startet.  Wie bereits erwähnt, ist die Eigenschaft <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nur auf <xref:System.Windows.Input.ICommandSource> anwendbar, wenn <xref:System.Windows.Input.ICommand> ein <xref:System.Windows.Input.RoutedCommand> ist.  Wenn <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> auf eine <xref:System.Windows.Input.ICommandSource> festgelegt und der entsprechende Befehl kein <xref:System.Windows.Input.RoutedCommand> ist, wird das Befehlsziel ignoriert.  
  
 Die Befehlsquelle kann das Befehlsziel explizit festlegen.  Wenn das Befehlsziel nicht definiert ist, wird das Element mit dem Tastaturfokus als Befehlsziel verwendet.  Einer der Vorteile daran, das Elements mit dem Tastaturfokus als Befehlsziel zu verwenden, ist die Tatsache, dass dies dem Anwendungsentwickler erlaubt, dieselbe Befehlsquelle zu verwenden, um einen Befehl für mehrere Ziele aufzurufen, ohne das Befehlsziel nachverfolgen zu müssen.  Wenn <xref:System.Windows.Controls.MenuItem> den Befehl **Paste** in einer Anwendung aufruft, die über ein <xref:System.Windows.Controls.TextBox>- und ein <xref:System.Windows.Controls.PasswordBox>-Steuerelement verfügt, kann das Ziel entweder <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.PasswordBox> sein, je nachdem, welches Steuerelement über den Tastaturfokus verfügt.  
  
 Im folgenden Beispiel wird das explizite Festlegen des Befehlsziels in Markup und der CodeBehind-Datei veranschaulicht.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>
### <a name="the-commandmanager"></a>Der CommandManager  
 <xref:System.Windows.Input.CommandManager> stellt eine Reihe von befehlsbezogenen Funktionen bereit.  Er bietet eine Reihe von statischen Methoden zum Hinzufügen und Entfernen der Ereignishandler <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> und <xref:System.Windows.Input.CommandManager.CanExecute> in und aus einem spezifischen Element.  Er ermöglicht das Registrieren der Objekte <xref:System.Windows.Input.CommandBinding> und <xref:System.Windows.Input.InputBinding> auf einer bestimmten Klasse.  <xref:System.Windows.Input.CommandManager> ermöglicht durch das Ereignis <xref:System.Windows.Input.CommandManager.RequerySuggested> außerdem das Benachrichtigen eines Befehls, wenn er das Ereignis <xref:System.Windows.Input.ICommand.CanExecuteChanged> auslösen soll.  
  
 Die Methode <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> zwingt <xref:System.Windows.Input.CommandManager> zum Auslösen des Ereignisses <xref:System.Windows.Input.CommandManager.RequerySuggested>.  Dies ist für Bedingungen nützlich, die einen Befehl nicht deaktivieren oder aktivieren sollen, aber keine Bedingungen sind, die <xref:System.Windows.Input.CommandManager> beachtet.  
  
<a name="Command_Library"></a>
## <a name="command-library"></a>Befehlsbibliothek  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vordefinierten Befehlen bereit.  Die Befehlsbibliothek besteht aus den folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> und <xref:System.Windows.Input.ComponentCommands>.  Diese Klassen stellen Befehle wie die Folgenden bereit: <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> und <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Viele dieser Befehle enthalten einen Satz von Standardeingabebindungen.  Wenn Sie z. b. angeben, dass die Anwendung den Kopier Befehl verarbeitet, erhalten Sie automatisch die Tastatur Bindung "STRG + C", und Sie erhalten auch Bindungen für andere Eingabegeräte, z. b. Tablet PC-Stift Gesten und Sprachinformationen.  
  
 Wenn Sie in den verschiedenen Bibliotheken mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf Befehle verweisen, können Sie normalerweise den Klassennamen der Bibliotheksklasse weglassen, die die statische Befehlseigenschaft verfügbar macht. In der Regel sind die Befehlsnamen als Zeichenfolgen eindeutig, und die besitzenden Typen sind vorhanden, um eine logische Gruppierung der Befehle bereitzustellen. Zur Mehrdeutigkeitsvermeidung sind sie nicht erforderlich. Sie können z.B. `Command="Cut"` anstelle des ausführlicheren `Command="ApplicationCommands.Cut"` angeben. Dies ist ein Hilfsmechanismus, der in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor für Befehle integriert ist (genauer betrachtet handelt es sich um ein Typkonverterverhalten von <xref:System.Windows.Input.ICommand> , auf das der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor zur Ladezeit verweist).  
  
<a name="creating_commands"></a>
## <a name="creating-custom-commands"></a>Erstellen von benutzerdefinierten Befehlen  
 Wenn die Befehle in den Klassen der Befehlsbibliothek nicht Ihren Bedürfnissen entsprechen, können Sie eigene Befehle erstellen.  Sie können auf zwei Arten und Weisen einen benutzerdefinierten Befehl erstellen.  Die Erste besteht darin, von Grund auf zu beginnen und die Schnittstelle <xref:System.Windows.Input.ICommand> zu implementieren.  Die andere, gängigere Möglichkeit besteht in der Erstellung eines <xref:System.Windows.Input.RoutedCommand> oder <xref:System.Windows.Input.RoutedUICommand>.  
  
 Ein Beispiel für das Erstellen eines benutzerdefinierten <xref:System.Windows.Input.RoutedCommand> finden Sie unter [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Input.RoutedCommand>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Input.InputBinding>
- <xref:System.Windows.Input.CommandManager>
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Implementieren von ICommandSource](how-to-implement-icommandsource.md)
- [How to: Add a Command to a MenuItem (Vorgehensweise: Hinzufügen eines Befehls zu einem MenuItem)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
- [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand)
