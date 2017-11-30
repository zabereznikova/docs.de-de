---
title: "Gewusst wie: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f38a6f900ee2b253708da4b63bdc2f474fa3ab1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Gewusst wie: Einbinden eines Befehls in ein Steuerelement ohne Befehlsunterstützung
Im folgende Beispiel wird gezeigt, wie zum Einbinden einer <xref:System.Windows.Input.RoutedCommand> auf eine <xref:System.Windows.Controls.Control> die nicht über eine integrierte Unterstützung für den Befehl.  Ein vollständiges Beispiel, das Befehle mit mehrere Quellen verknüpft, finden Sie im Beispiel unter [Create a Custom RoutedCommand Sample (Erstellen eines benutzerdefinierten „RoutedCommand“-Beispiels)](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine Bibliothek mit allgemeinen Befehlen bereit, die Anwendungsprogrammierer häufig nutzen.  Die Klassen, die Befehlsbibliothek sind: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statische <xref:System.Windows.Input.RoutedCommand> Geben Sie Objekte, die diese Klassen bilden keine Logik.  Die Logik für den Befehl bezieht sich auf den Befehl mit einem <xref:System.Windows.Input.CommandBinding>.  Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Unterstützung für einige der Befehle in der Befehlsbibliothek erstellt haben.  <xref:System.Windows.Controls.TextBox>, z. B. unterstützt viele der Anwendung Bearbeitungsbefehle wie z. B. <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Der Anwendungsentwickler muss gar nichts Besonderes tun, um diese Befehle zum Arbeiten mit diesen Steuerelementen zu erhalten.  Wenn die <xref:System.Windows.Controls.TextBox> ist das Befehlsziel, wenn der Befehl ausgeführt wird, wird er behandeln, den Befehl mithilfe der <xref:System.Windows.Input.CommandBinding> , die in das Steuerelement erstellt wird.  
  
 Im folgenden wird gezeigt, wie eine <xref:System.Windows.Controls.Button> als Befehlsquelle für die <xref:System.Windows.Input.ApplicationCommands.Open%2A> Befehl.  Ein <xref:System.Windows.Input.CommandBinding> erstellt wird, ordnet das angegebene <xref:System.Windows.Input.CanExecuteRoutedEventHandler> und <xref:System.Windows.Input.CanExecuteRoutedEventHandler> mit der <xref:System.Windows.Input.RoutedCommand>.  
  
 Zuerst wird die Befehlsquelle erstellt.  Ein <xref:System.Windows.Controls.Button> als die Befehlsquelle verwendet wird.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Als Nächstes wird die <xref:System.Windows.Input.ExecutedRoutedEventHandler> und <xref:System.Windows.Input.CanExecuteRoutedEventHandler> erstellt werden.  Die <xref:System.Windows.Input.ExecutedRoutedEventHandler> öffnet einfach eine <xref:System.Windows.MessageBox> um anzugeben, dass der Befehl ausgeführt.  Die <xref:System.Windows.Input.CanExecuteRoutedEventHandler> legt die <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> Eigenschaft `true`.  Normalerweise kann der führen Handler würde führen Sie eine robustere Überprüfungen aus, um festzustellen, ob der Befehl für das aktuelle Befehlsziel ausgeführt werden konnte.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Schließlich eine <xref:System.Windows.Input.CommandBinding> wird im Stammverzeichnis erstellt <xref:System.Windows.Window> der Anwendung, die die Routingereignishandler ordnet die <xref:System.Windows.Input.ApplicationCommands.Open%2A> Befehl.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Einbinden eines Befehls in ein Steuerelement mit Befehlsunterstützung](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
