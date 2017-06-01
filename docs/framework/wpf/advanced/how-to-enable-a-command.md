---
title: "Gewusst wie: Aktivieren eines Befehls | Microsoft Docs"
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
  - "CommandBindings"
  - "Befehle"
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Aktivieren eines Befehls
Im folgenden Beispiel wird veranschaulicht, wie Befehle in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwendet werden.  In dem Beispiel wird gezeigt, wie ein <xref:System.Windows.Input.RoutedCommand> einer <xref:System.Windows.Controls.Button> zugeordnet wird, wie eine <xref:System.Windows.Input.CommandBinding> erstellt wird und wie Ereignishandler erstellt werden, mit denen <xref:System.Windows.Input.RoutedCommand> implementiert wird.  Weitere Informationen über Befehle finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Beispiel  
 Mit dem ersten Codeabschnitt wird die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] erstellt, die aus einer <xref:System.Windows.Controls.Button> und einem <xref:System.Windows.Controls.StackPanel> besteht. Dann wird eine <xref:System.Windows.Input.CommandBinding> erstellt, mit der die Befehlshandler dem <xref:System.Windows.Input.RoutedCommand> zugeordnet werden.  
  
 Die <xref:System.Windows.Input.ICommandSource.Command%2A>\-Eigenschaft der <xref:System.Windows.Controls.Button> ist dem <xref:System.Windows.Input.ApplicationCommands.Close%2A>\-Befehl zugeordnet.  
  
 <xref:System.Windows.Input.CommandBinding> wird der <xref:System.Windows.Input.CommandBindingCollection> des Stamm\-<xref:System.Windows.Window> hinzugefügt.  Die Ereignishandler <xref:System.Windows.Input.CommandBinding.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> werden an diese Bindung angefügt und werden dem <xref:System.Windows.Input.ApplicationCommands.Close%2A>\-Befehl zugeordnet.  
  
 Ohne <xref:System.Windows.Input.CommandBinding> gibt es keine Befehlslogik, sondern nur einen Mechanismus zum Aufrufen des Befehls.  Wenn auf <xref:System.Windows.Controls.Button> geklickt wird, wird <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> gefolgt von <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent> für das Befehlsziel ausgelöst.   Diese Ereignisse durchlaufen die Elementstruktur auf der Suche nach einer <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl.   Da <xref:System.Windows.RoutedEvent> die Elementstruktur abwärts und aufwärts durchläuft, sollte <xref:System.Windows.Input.CommandBinding> mit Bedacht gesetzt werden.  Befindet sich <xref:System.Windows.Input.CommandBinding> auf einem dem Befehlsziel gleichgeordneten Element oder auf einem anderen Knoten, der nicht zur Route von <xref:System.Windows.RoutedEvent> gehört, wird auf <xref:System.Windows.Input.CommandBinding> nicht zugegriffen.  
  
 [!code-xml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 Der nächste Codeabschnitt implementiert die Ereignishandler <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 Der <xref:System.Windows.Input.CommandManager.Executed>\-Handler ruft eine Methode auf, um die geöffnete Datei zu schließen.  Der <xref:System.Windows.Input.CommandBinding.CanExecute>\-Handler ruft eine Methode auf, um zu bestimmen, ob eine Datei geöffnet ist.  Ist eine Datei geöffnet, wird <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> auf `true` festgelegt. Andernfalls wird er auf `false` festgelegt.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)