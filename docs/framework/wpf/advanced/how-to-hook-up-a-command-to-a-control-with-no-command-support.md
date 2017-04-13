---
title: "Gewusst wie: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterst&#252;tzung | Microsoft Docs"
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
  - "Klassen, Steuerelement, Anfügen eines RoutedCommand"
  - "Klassen, RoutedCommand, Anfügen an ein Steuerelement"
  - "Control-Klasse, Anfügen eines RoutedCommand"
  - "RoutedCommand-Klasse, Anfügen an ein Steuerelement"
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterst&#252;tzung
Das folgende Beispiel zeigt, wie Sie einen <xref:System.Windows.Input.RoutedCommand> in ein <xref:System.Windows.Controls.Control> einbinden, das nicht über eine integrierte Unterstützung für den Befehl verfügt.  Ein vollständiges Beispiel, in dem Befehle in mehrere Quellen eingebunden werden, finden Sie unter [Beispiel für das Erstellen eines benutzerdefinierten "RoutedCommand"](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine Bibliothek mit allgemeinen Befehlen bereit, die Anwendungsprogrammierer häufig nutzen.  Die Befehlsbibliothek enthält die folgenden Klassen: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statischen <xref:System.Windows.Input.RoutedCommand>\-Objekte, aus denen diese Klassen bestehen, stellen keine Befehlslogik bereit.  Die Logik für den Befehl wird dem Befehl mithilfe von <xref:System.Windows.Input.CommandBinding> bereitgestellt.  Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Unterstützung für einige Befehle der Befehlsbibliothek.  <xref:System.Windows.Controls.TextBox> unterstützt zum Beispiel viele Bearbeitungsbefehle der Anwendung, wie <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Anwendungsentwickler müssen keine speziellen Schritte ausführen, damit diese Befehle mit diesen Steuerelementen funktionieren.  Wenn das <xref:System.Windows.Controls.TextBox> das Befehlsziel ist, wenn der Befehl ausgeführt wird, behandelt es den Befehl mithilfe des <xref:System.Windows.Input.CommandBinding>\-Elements, das in das Steuerelement integriert ist.  
  
 Das folgende Beispiel zeigt, wie Sie ein <xref:System.Windows.Controls.Button> als Befehlsquelle für den <xref:System.Windows.Input.ApplicationCommands.Open%2A>\-Befehl verwenden.  Eine <xref:System.Windows.Input.CommandBinding> wird erstellt, die dem <xref:System.Windows.Input.RoutedCommand> die angegebenen <xref:System.Windows.Input.CanExecuteRoutedEventHandler> und <xref:System.Windows.Input.CanExecuteRoutedEventHandler> zuordnet.  
  
 Zuerst wird die Befehlsquelle erstellt.  Eine <xref:System.Windows.Controls.Button> wird als Befehlsquelle verwendet.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Anschließend werden <xref:System.Windows.Input.ExecutedRoutedEventHandler> und <xref:System.Windows.Input.CanExecuteRoutedEventHandler> erstellt.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet einfach ein <xref:System.Windows.MessageBox>, um die Ausführung des Befehls zu kennzeichnen.  Der <xref:System.Windows.Input.CanExecuteRoutedEventHandler> setzt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>\-Eigenschaft auf `true`.  Normalerweise nimmt der CanExecute\-Handler gründlichere Überprüfungen vor, um festzustellen, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden konnte.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Schließlich wird eine <xref:System.Windows.Input.CommandBinding> für das Stamm\-<xref:System.Windows.Window> der Anwendung erstellt, die die Routingereignishandler dem <xref:System.Windows.Input.ApplicationCommands.Open%2A> zuordnet.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)