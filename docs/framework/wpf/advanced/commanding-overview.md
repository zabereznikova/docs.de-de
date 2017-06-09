---
title: "Befehls&#252;bersicht | Microsoft Docs"
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
  - "Klassen, CommandBinding"
  - "Befehlsbibliothek"
  - "CommandBindings"
  - "Befehle"
  - "CommandManager"
  - "Befehle, Definition von"
  - "IcommandSource-Schnittstellen"
  - "Schnittstellen, ICommandSource"
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Befehls&#252;bersicht
<a name="introduction"></a> Die Befehle sind ein Eingabemechanismus in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], wobei die Eingabebehandlung auf einer semantischeren Ebene als bei der Geräteeingabe erfolgt.  Beispiele für Befehle sind die Vorgänge **Kopieren**, **Ausschneiden** und **Einfügen**, die in vielen Anwendungen verwendet werden.  
  
 In dieser Übersicht wird definiert, welche Befehle Teil von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind, welche Klassen Teil des Befehlsmodells sind und wie Sie Befehle in Ihren Anwendungen verwenden und erstellen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Was sind Befehle?](#commands_at_10000_feet)  
  
-   [Einfaches Befehlsbeispiel für WPF](#simple_command)  
  
-   [Vier Hauptbegriffe für WPF\-Befehle](#Four_main_Concepts)  
  
-   [Befehlsbibliothek](#Command_Library)  
  
-   [Erstellen von benutzerdefinierten Befehlen](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## Was sind Befehle?  
 Befehle erfüllen mehrere Zwecke.  Der erste Zweck besteht in der Trennung der Semantik und des Objekts, von dem ein Befehl aus der Logik aufgerufen wird, durch die der Befehl ausgeführt wird.  Auf diese Weise können mehrere unterschiedliche Quellen dieselbe Befehlslogik aufrufen und diese für verschiedene Ziele anpassen.  So können beispielsweise die Bearbeitungsvorgänge **Kopieren**, **Ausschneiden** und **Einfügen**, die in den meisten Anwendungen zur Verfügung stehen, durch unterschiedliche Benutzeraktionen aufgerufen werden, sofern diese mit Befehlen implementiert wurden.  In einer Anwendung kann es dem Benutzer beispielsweise ermöglicht werden, ausgewählte Objekte oder ausgewählten Text durch Klicken auf eine Schaltfläche, durch Auswählen eines Menüelements oder durch Drücken einer Tastenkombination \(beispielsweise STRG\+X\) auszuschneiden.  Mit Befehlen lässt sich jede Art von Benutzeraktion an die gleiche Logik binden.  
  
 Ein weiterer Zweck von Befehlen besteht darin anzugeben, ob eine Aktion verfügbar ist.  Bleiben wir bei dem Beispiel des Ausschneidens von Objekten oder Text: Diese Aktion ist nur sinnvoll, wenn zuvor etwas ausgewählt wurde.  Versucht ein Benutzer, ein Objekt oder Text auszuschneiden, ohne zuvor etwas ausgewählt zu haben, passiert nichts.  In vielen Anwendungen werden deshalb Schaltflächen und Menüelemente deaktiviert, damit der Benutzer weiß, ob eine Aktion ausgeführt werden kann.  Durch Implementieren der <xref:System.Windows.Input.ICommand.CanExecute%2A>\-Methode kann von einem Befehl angegeben werden, ob eine Aktion ausgeführt werden kann.  Von einer Schaltfläche kann das <xref:System.Windows.Input.ICommand.CanExecuteChanged>\-Ereignis abonniert werden. Wird nun von <xref:System.Windows.Input.ICommand.CanExecute%2A> der Wert `false` zurückgegeben, wird die Schaltfläche deaktiviert. Wird von <xref:System.Windows.Input.ICommand.CanExecute%2A> dagegen der Wert `true` zurückgegeben, wird die Schaltfläche aktiviert.  
  
 Die Semantik eines Befehls kann über Anwendungen und Klassen hinweg konsistent sein, aber die Logik der Aktion ist jeweils spezifisch für das Objekt, für das die Aktion ausgeführt wird.  Über die Tastenkombination STRG\+X wird zwar der Befehl **Ausschneiden** in Textklassen, Imageklassen und in Webbrowsern aufgerufen, die eigentliche Logik zum Ausführen der Operation **Ausschneiden** wird jedoch von der Anwendung definiert, von der der Ausschneidevorgang ausgeführt wird.  Mithilfe von <xref:System.Windows.Input.RoutedCommand> kann die Logik von Clients implementiert werden.  Von einem Textobjekt kann der ausgewählte Text ausgeschnitten und in die Zwischenablage eingefügt werden, wohingegen von einem Imageobjekt das ausgewählte Image ausgeschnitten wird.  Beim Behandeln des <xref:System.Windows.Input.CommandManager.Executed>\-Ereignisses durch eine Anwendung erhält die Anwendung Zugriff auf das Ziel des Befehls, und je nach Art des Ziels kann die entsprechende Aktion ausgeführt werden.  
  
<a name="simple_command"></a>   
## Einfaches Befehlsbeispiel für WPF  
 Die einfachste Art der Anwendung eines Befehls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist das Verwenden eines vordefinierten <xref:System.Windows.Input.RoutedCommand>\-Elements aus einer der Befehlsbibliotheksklassen, das Verwenden eines Steuerelements, das über eine systemeigene Unterstützung zum Verarbeiten des Befehls verfügt, und das Verwenden eines Steuerelements, das über eine systemeigene Unterstützung zum Aufrufen eines Befehls verfügt.  Der Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> ist einer der vordefinierten Befehle in der <xref:System.Windows.Input.ApplicationCommands>\-Klasse.  Das <xref:System.Windows.Controls.TextBox>\-Steuerelement weist eine integrierte Logik für die Verarbeitung des Befehls <xref:System.Windows.Input.ApplicationCommands.Paste%2A> auf.  Und die <xref:System.Windows.Controls.MenuItem>\-Klasse verfügt über eine systemeigene Unterstützung zum Aufrufen von Befehlen.  
  
 Das folgende Beispiel zeigt, wie Sie ein <xref:System.Windows.Controls.MenuItem> so einrichten, dass beim Klicken darauf der Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> für ein <xref:System.Windows.Controls.TextBox>\-Steuerelement aufgerufen wird, vorausgesetzt, das <xref:System.Windows.Controls.TextBox>\-Steuerelement hat den Tastaturfokus.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## Vier Hauptbegriffe für WPF\-Befehle  
 Das Modell der weitergeleiteten Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann in vier Hauptbegriffe unterteilt werden: Befehl, Befehlsquelle, Befehlsziel und Befehlsbindung:  
  
-   Der *Befehl* ist die Aktion, die ausgeführt werden soll.  
  
-   Die *Befehlsquelle* ist das Objekt, das den Befehl aufruft.  
  
-   Das *Befehlsziel* ist das Objekt, für das der Befehl ausgeführt wird.  
  
-   Die *Befehlsbindung* ist das Objekt, das dem Befehl die Befehlslogik zuordnet.  
  
 Im obigen Beispiel ist der Befehl <xref:System.Windows.Input.ApplicationCommands.Paste%2A> der Befehl, <xref:System.Windows.Controls.MenuItem> ist die Befehlsquelle, <xref:System.Windows.Controls.TextBox> ist das Befehlsziel und die Befehlsbindung wird vom <xref:System.Windows.Controls.TextBox>\-Steuerelement bereitgestellt.  Dabei ist zu beachten, dass es nicht immer der Fall ist, dass die <xref:System.Windows.Input.CommandBinding> von dem Steuerelement bereitgestellt wird, bei dem es sich um die Befehlszielklasse handelt.  Häufig muss die <xref:System.Windows.Input.CommandBinding> vom Anwendungsentwickler erstellt werden, oder die <xref:System.Windows.Input.CommandBinding> muss einem Vorgänger des Befehlsziels zugeordnet werden.  
  
<a name="Commands"></a>   
### Befehle  
 Befehle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden durch Implementieren der <xref:System.Windows.Input.ICommand>\-Schnittstelle implementiert.  Von <xref:System.Windows.Input.ICommand> werden zwei Methoden \(<xref:System.Windows.Input.ICommand.Execute%2A> und <xref:System.Windows.Input.ICommand.CanExecute%2A>\) sowie ein Ereignis \(<xref:System.Windows.Input.ICommand.CanExecuteChanged>\) verfügbar gemacht.  <xref:System.Windows.Input.ICommand.Execute%2A> führt die Aktionen aus, die dem Befehl zugeordnet sind. <xref:System.Windows.Input.ICommand.CanExecute%2A> bestimmt, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden kann.  <xref:System.Windows.Input.ICommand.CanExecuteChanged> wird ausgelöst, wenn der Befehls\-Manager, der die Befehlsabläufe zentral verwaltet, eine Änderung der Befehlsquelle erkennt, die einen ausgelösten, aber von der Befehlsbindung noch nicht ausgeführten Befehl ggf. ungültig macht.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung von <xref:System.Windows.Input.ICommand> ist die <xref:System.Windows.Input.RoutedCommand>\-Klasse, die im Mittelpunkt dieser Übersicht steht.  
  
 Die Hauptquellen der Eingabe unter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die Maus, die Tastatur, Freihandeingaben und weitergeleitete Befehle.  Bei den stärker geräteorientierten Eingaben wird ein <xref:System.Windows.RoutedEvent> verwendet, um Objekte auf einer Anwendungsseite davon in Kenntnis zu setzen, dass ein Eingabeereignis erfolgt ist.  Bei einem <xref:System.Windows.Input.RoutedCommand> verhält es sich genauso.  Die Methoden <xref:System.Windows.Input.RoutedCommand.Execute%2A> und <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> eines <xref:System.Windows.Input.RoutedCommand> enthalten die Anwendungslogik des Befehls nicht, sondern lösen Routingereignisse aus, die die Elementstruktur per Tunneling und Bubbling durchlaufen, bis sie auf ein Objekt mit einer <xref:System.Windows.Input.CommandBinding> treffen.  Die <xref:System.Windows.Input.CommandBinding> enthält die Handler für diese Ereignisse und stellt die Handler dar, die den Befehl ausführen.  Weitere Informationen zum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisrouting finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Die <xref:System.Windows.Input.RoutedCommand.Execute%2A>\-Methode eines <xref:System.Windows.Input.RoutedCommand> löst die Ereignisse <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> für das Befehlsziel aus.  Die <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>\-Methode eines <xref:System.Windows.Input.RoutedCommand> löst die Ereignisse <xref:System.Windows.Input.CommandManager.CanExecute> und <xref:System.Windows.Input.CommandManager.PreviewCanExecute> für das Befehlsziel aus.  Diese Ereignisse durchlaufen die Elementstruktur per Tunneling und Bubbling, bis sie auf ein Objekt treffen, das über eine <xref:System.Windows.Input.CommandBinding> für den jeweiligen Befehl verfügt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine Reihe von gängigen weitergeleiteten Befehlen, die auf mehrere Klassen verteilt sind: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> und <xref:System.Windows.Documents.EditingCommands>.  Diese Klassen umfassen nur die <xref:System.Windows.Input.RoutedCommand>\-Objekte, nicht die Implementierungslogik des Befehls.  Für die Implementierungslogik ist das Objekt verantwortlich, für das der Befehl ausgeführt wird.  
  
<a name="Command_Sources"></a>   
### Befehlsquellen  
 Eine Befehlsquelle ist das Objekt, das den Befehl aufruft.  Beispiele für Befehlsquellen sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Input.KeyGesture>.  
  
 Befehlsquellen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementieren im Allgemeinen die <xref:System.Windows.Input.ICommandSource>\-Schnittstelle.  
  
 <xref:System.Windows.Input.ICommandSource> legt drei Eigenschaften offen: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> und <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> ist der Befehl, der ausgeführt wird, wenn die Befehlsquelle aufgerufen wird.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt, für das der Befehl ausgeführt wird.  Dabei ist zu beachten, dass in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>\-Eigenschaft für <xref:System.Windows.Input.ICommandSource> nur anwendbar ist, wenn es sich bei <xref:System.Windows.Input.ICommand> um einen <xref:System.Windows.Input.RoutedCommand> handelt.  Wenn das <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> für eine <xref:System.Windows.Input.ICommandSource> festgelegt wurde und der entsprechende Befehl kein <xref:System.Windows.Input.RoutedCommand> ist, wird das Befehlsziel ignoriert.  Wenn das <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> nicht festgelegt ist, wird das Element mit dem Tastaturfokus als Befehlsziel verwendet.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ist ein benutzerdefinierter Datentyp, der verwendet wird, um Informationen an die Handler zu übergeben, die den Befehl implementieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen, die <xref:System.Windows.Input.ICommandSource> implementieren, sind <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> und <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> und <xref:System.Windows.Documents.Hyperlink> rufen einen Befehl auf, wenn darauf geklickt wird, und eine <xref:System.Windows.Input.InputBinding> ruft einen Befehl auf, wenn die zugeordnete <xref:System.Windows.Input.InputGesture> ausgeführt wird.  
  
 Das folgende Beispiel zeigt, wie Sie ein <xref:System.Windows.Controls.MenuItem> in einem <xref:System.Windows.Controls.ContextMenu> als Befehlsquelle für den <xref:System.Windows.Input.ApplicationCommands.Properties%2A>\-Befehl verwenden.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Normalerweise überwacht eine Befehlsquelle das <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>\-Ereignis.  Dieses Ereignis benachrichtigt die Befehlsquelle darüber, dass sich die Fähigkeit des Befehls, für das aktuelle Befehlsziel ausgeführt zu werden, ggf. geändert hat.  Die Befehlsquelle kann den aktuellen Status für den <xref:System.Windows.Input.RoutedCommand> abfragen, indem sie die <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>\-Methode verwendet.  Die Befehlsquelle kann sich dann selbst deaktivieren, wenn der Befehl nicht ausgeführt werden kann.  Ein Beispiel hierfür ist ein <xref:System.Windows.Controls.MenuItem>, das sich selbst abblendet, wenn ein Befehl nicht ausgeführt werden kann.  
  
 Eine <xref:System.Windows.Input.InputGesture> kann als Befehlsquelle verwendet werden.  Zwei Typen von Eingabeaktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind <xref:System.Windows.Input.KeyGesture> und <xref:System.Windows.Input.MouseGesture>.  Sie können sich eine <xref:System.Windows.Input.KeyGesture> als Tastenkombination vorstellen, z. B. STRG\+C.  Eine <xref:System.Windows.Input.KeyGesture> besteht aus einem <xref:System.Windows.Input.Key> und verschiedenen <xref:System.Windows.Input.ModifierKeys>.  Eine <xref:System.Windows.Input.MouseGesture> besteht aus einer <xref:System.Windows.Input.MouseAction> und einer Reihe optionaler <xref:System.Windows.Input.ModifierKeys>.  
  
 Damit eine <xref:System.Windows.Input.InputGesture> als Befehlsquelle fungieren kann, muss sie einem Befehl zugeordnet sein.  Es gibt einige Möglichkeiten, dies zu erreichen.  Ein Ansatz besteht darin, eine <xref:System.Windows.Input.InputBinding> zu verwenden.  
  
 Das folgende Beispiel zeigt, wie Sie zwischen einer <xref:System.Windows.Input.KeyGesture> und einem <xref:System.Windows.Input.RoutedCommand> eine <xref:System.Windows.Input.KeyBinding> erstellen.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Eine andere Möglichkeit, eine <xref:System.Windows.Input.InputGesture> einem <xref:System.Windows.Input.RoutedCommand> zuzuordnen, ist das Hinzufügen der <xref:System.Windows.Input.InputGesture> zur <xref:System.Windows.Input.InputGestureCollection> des <xref:System.Windows.Input.RoutedCommand>\-Elements.  
  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Input.KeyGesture> der <xref:System.Windows.Input.InputGestureCollection> eines <xref:System.Windows.Input.RoutedCommand>\-Elements hinzufügen.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### CommandBinding  
 Eine <xref:System.Windows.Input.CommandBinding> ordnet einen Befehl den Ereignishandlern zu, die den Befehl implementieren.  
  
 Die <xref:System.Windows.Input.CommandBinding>\-Klasse enthält eine <xref:System.Windows.Input.CommandBinding.Command%2A>\-Eigenschaft sowie die Ereignisse <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> und <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> ist der Befehl, dem die <xref:System.Windows.Input.CommandBinding> zugeordnet wird.  Die Ereignishandler, die den Ereignissen <xref:System.Windows.Input.CommandBinding.PreviewExecuted> und <xref:System.Windows.Input.CommandBinding.Executed> zugeordnet sind, implementieren die Befehlslogik.  Die Ereignishandler, die den Ereignissen <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> und <xref:System.Windows.Input.CommandBinding.CanExecute> zugeordnet sind, bestimmen, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden kann.  
  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Input.CommandBinding> für das <xref:System.Windows.Window>\-Stammelement einer Anwendung erstellen.  Die <xref:System.Windows.Input.CommandBinding> ordnet den <xref:System.Windows.Input.ApplicationCommands.Open%2A>\-Befehl den Handlern <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> zu.  
  
 [!code-xml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Anschließend werden der <xref:System.Windows.Input.ExecutedRoutedEventHandler> und ein <xref:System.Windows.Input.CanExecuteRoutedEventHandler> erstellt.  Der <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet ein <xref:System.Windows.MessageBox>, in dem eine Zeichenfolge angezeigt wird, die aussagt, dass der Befehl ausgeführt wurde.  Der <xref:System.Windows.Input.CanExecuteRoutedEventHandler> setzt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>\-Eigenschaft auf `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Eine <xref:System.Windows.Input.CommandBinding> ist an ein bestimmtes Objekt angefügt, z. B. an das <xref:System.Windows.Window>\-Stammelement der Anwendung oder eines Steuerelements.  Das Objekt, an das die <xref:System.Windows.Input.CommandBinding> angefügt ist, definiert den Bindungsbereich.  Eine <xref:System.Windows.Input.CommandBinding>, die an einen Vorgänger des Befehlsziels angefügt ist, kann z. B. vom <xref:System.Windows.Input.CommandBinding.Executed>\-Ereignis erreicht werden, aber eine <xref:System.Windows.Input.CommandBinding>, die an einen Nachfolger des Befehlsziels angefügt ist, kann nicht erreicht werden.  Dies ist eine direkte Folge der Art und Weise, wie ein <xref:System.Windows.RoutedEvent> die Struktur per Tunneling und Bubbling von einem Objekt durchläuft, das das Ereignis auslöst.  
  
 In einigen Situationen ist die <xref:System.Windows.Input.CommandBinding> an das Befehlsziel selbst angefügt, z. B. bei der <xref:System.Windows.Controls.TextBox>\-Klasse und den Befehlen <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> und <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  Häufig ist es einfacher, die <xref:System.Windows.Input.CommandBinding> an einen Vorgänger des Befehlsziels anzufügen, z. B. an das <xref:System.Windows.Window>\-Hauptfenster oder das Application\-Objekt, besonders wenn eine <xref:System.Windows.Input.CommandBinding> für mehrere Befehlsziele verwendet werden kann.  Dies sind Entwurfsentscheidungen, die Sie beim Erstellen der Befehlsinfrastruktur berücksichtigen sollten.  
  
<a name="Commane_Target"></a>   
### Befehlsziel  
 Das Befehlsziel ist das Element, für das der Befehl ausgeführt wird.  Bei einem <xref:System.Windows.Input.RoutedCommand> ist das Befehlsziel das Element, bei dem das Routing von <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandManager.CanExecute> beginnt.  Wie bereits erwähnt, ist in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>\-Eigenschaft für <xref:System.Windows.Input.ICommandSource> nur anwendbar ist, wenn es sich bei <xref:System.Windows.Input.ICommand> um einen <xref:System.Windows.Input.RoutedCommand> handelt.  Wenn das <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> für eine <xref:System.Windows.Input.ICommandSource> festgelegt wurde und der entsprechende Befehl kein <xref:System.Windows.Input.RoutedCommand> ist, wird das Befehlsziel ignoriert.  
  
 Die Befehlsquelle kann das Befehlsziel explizit festlegen.  Wenn das Befehlsziel nicht definiert ist, wird das Element mit dem Tastaturfokus als Befehlsziel verwendet.  Einer der Vorteile der Verwendung des Elements mit dem Tastaturfokus als Befehlsziel besteht darin, dass Anwendungsentwickler dieselbe Befehlsquelle verwenden können, um einen Befehl für mehrere Ziele aufzurufen, ohne das Befehlsziel verfolgen zu müssen.  Wenn ein <xref:System.Windows.Controls.MenuItem> z. B. den Befehl **Einfügen** in einer Anwendung aufruft, die über ein <xref:System.Windows.Controls.TextBox>\- und ein <xref:System.Windows.Controls.PasswordBox>\-Steuerelement verfügt, kann das Ziel entweder das <xref:System.Windows.Controls.TextBox>\-oder das <xref:System.Windows.Controls.PasswordBox>\-Steuerelement sein. Dies ist davon abhängig, welches Steuerelement gerade den Tastaturfokus besitzt.  
  
 Das folgende Beispiel zeigt, wie Sie das Befehlsziel in Markup und in Code\-Behind explizit festlegen.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### Der CommandManager  
 Der <xref:System.Windows.Input.CommandManager> stellt verschiedene befehlsbezogene Funktionen bereit.  Er bietet Benutzern eine Reihe von statischen Methoden zum Hinzufügen und Entfernen der Ereignishandler <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> und <xref:System.Windows.Input.CommandManager.CanExecute> zu einem bestimmten Element bzw. aus einem bestimmten Element.  Sie können ihn verwenden, um <xref:System.Windows.Input.CommandBinding>\- und <xref:System.Windows.Input.InputBinding>\-Objekte für eine spezifische Klasse zu registrieren.  Mithilfe von <xref:System.Windows.Input.CommandManager> können Sie über das <xref:System.Windows.Input.CommandManager.RequerySuggested>\-Ereignis außerdem einem Befehl mitteilen, wann dieser das <xref:System.Windows.Input.ICommand.CanExecuteChanged>\-Ereignis auslösen soll.  
  
 Die <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A>\-Methode zwingt den <xref:System.Windows.Input.CommandManager>, das <xref:System.Windows.Input.CommandManager.RequerySuggested>\-Ereignis auszulösen.  Dies ist für Bedingungen nützlich, die einen Befehl deaktivieren bzw. aktivieren sollen, ohne dass der <xref:System.Windows.Input.CommandManager> über diese Bedingungen informiert ist.  
  
<a name="Command_Library"></a>   
## Befehlsbibliothek  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vordefinierten Befehlen bereit.  Die Befehlsbibliothek besteht aus den folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> und <xref:System.Windows.Input.ComponentCommands>.  Diese Klassen stellen Befehle wie <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> und <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> und <xref:System.Windows.Input.MediaCommands.Pause%2A> bereit.  
  
 Viele dieser Befehle enthalten verschiedene standardmäßige Eingabebindungen.  Wenn Sie z. B. eingeben, dass Ihre Anwendung den Kopierbefehl behandelt, erhalten Sie automatisch die Tastaturbindung "STRG\+C". Sie erhalten auch Bindungen für andere Eingabegeräte, z. B. [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)]\-Stiftbewegungen und \-Sprachinformationen.  
  
 Wenn Sie mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] auf Befehle in den verschiedenen Bibliotheken verweisen, können Sie normalerweise den Klassennamen der Bibliotheksklasse weglassen, die die statische Befehlseigenschaft offenlegt.  In der Regel sind Befehlsnamen als Zeichenfolgen eindeutig, und die besitzenden Typen sind vorhanden, um eine logische Gruppierung der Befehle zu ermöglichen. Sie sind jedoch nicht erforderlich, um die Eindeutigkeit sicherzustellen.  Sie können z. B. `Command="Cut"` anstelle des ausführlicheren `Command="ApplicationCommands.Cut"` angeben.  Dies ist ein Mechanismus, der die Benutzerfreundlichkeit fördert und in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor für Befehle integriert ist \(genauer gesagt handelt es sich um ein Typkonverterverhalten von <xref:System.Windows.Input.ICommand>, auf das der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor zur Ladezeit verweist\).  
  
<a name="creating_commands"></a>   
## Erstellen von benutzerdefinierten Befehlen  
 Wenn die Befehle in den Befehlsbibliotheksklassen für Ihre Anforderungen nicht ausreichen, können Sie Ihre eigenen Befehle erstellen.  Es gibt zwei Möglichkeiten, einen benutzerdefinierten Befehl zu erstellen.  Die erste Möglichkeit besteht darin, von Grund auf zu beginnen und die <xref:System.Windows.Input.ICommand>\-Schnittstelle zu implementieren.  Eine gängigere Möglichkeit besteht darin, einen <xref:System.Windows.Input.RoutedCommand> oder einen <xref:System.Windows.Input.RoutedUICommand> zu erstellen.  
  
 Ein Beispiel für die Erstellung einer benutzerdefinierten Version von <xref:System.Windows.Input.RoutedCommand> finden Sie unter [Beispiel für das Erstellen eines benutzerdefinierten "RoutedCommand"](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## Siehe auch  
 <xref:System.Windows.Input.RoutedCommand>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Input.InputBinding>   
 <xref:System.Windows.Input.CommandManager>   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Implementieren von ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/de-de/013d68a0-5373-4a68-bd91-5de574307370)   
 [Beispiel für das Erstellen eines benutzerdefinierten "RoutedCommand"](http://go.microsoft.com/fwlink/?LinkID=159980)