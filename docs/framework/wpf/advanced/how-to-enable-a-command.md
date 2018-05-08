---
title: 'Gewusst wie: Aktivieren eines Befehls'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: 81ae2e46c4fdd8b46e2b72b9a1430437ebfe97b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-a-command"></a>Gewusst wie: Aktivieren eines Befehls
Im folgenden Beispiel wird veranschaulicht, wie Befehle in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Im Beispiel veranschaulicht das Zuordnen einer <xref:System.Windows.Input.RoutedCommand> auf eine <xref:System.Windows.Controls.Button>, erstellen eine <xref:System.Windows.Input.CommandBinding>, und erstellen Sie die Ereignishandler die implementieren die <xref:System.Windows.Input.RoutedCommand>.  Weitere Informationen über Befehle finden Sie unter der [Befehle (Übersicht)](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Beispiel  
 Der erste Abschnitt der Code erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], besteht aus dem ein <xref:System.Windows.Controls.Button> und ein <xref:System.Windows.Controls.StackPanel>, und erstellt eine <xref:System.Windows.Input.CommandBinding> , die der Befehlshandler mit ordnet die <xref:System.Windows.Input.RoutedCommand>.  
  
 Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft von der <xref:System.Windows.Controls.Button> zugeordnet ist die <xref:System.Windows.Input.ApplicationCommands.Close%2A> Befehl.  
  
 Die <xref:System.Windows.Input.CommandBinding> wird hinzugefügt, um die <xref:System.Windows.Input.CommandBindingCollection> des Stamms <xref:System.Windows.Window>. Die <xref:System.Windows.Input.CommandBinding.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> Ereignishandler diese Bindung angefügt und zugeordnet werden die <xref:System.Windows.Input.ApplicationCommands.Close%2A> Befehl.  
  
 Ohne die <xref:System.Windows.Input.CommandBinding> keine Befehlslogik, die nur einen Mechanismus zum Aufrufen des Befehls vorhanden ist.  Wenn die <xref:System.Windows.Controls.Button> geklickt wird, die <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> wird ausgelöst, für das Befehlsziel gefolgt von der <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Diese Ereignisse durchlaufen die Elementstruktur nach einem <xref:System.Windows.Input.CommandBinding> für diesen bestimmten Befehl.  Es ist zu beachten, dass, weil <xref:System.Windows.RoutedEvent> und aufwärts durch die Elementstruktur, muss darauf geachtet werden, aus denen die <xref:System.Windows.Input.CommandBinding> abgelegt wird.   Wenn die <xref:System.Windows.Input.CommandBinding> befindet sich auf ein gleichgeordnetes Element eines das Befehlsziel oder einen anderen Knoten, der nicht auf die Route des ist die <xref:System.Windows.RoutedEvent>, die <xref:System.Windows.Input.CommandBinding> nicht zugegriffen werden.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 Der nächste Abschnitt der Code implementiert die <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> -Ereignishandler.  
  
 Die <xref:System.Windows.Input.CommandManager.Executed> Handler Ruft eine Methode, um die geöffnete Datei zu schließen.  Die <xref:System.Windows.Input.CommandBinding.CanExecute> Handler aufruft, eine Methode, um zu bestimmen, ob eine Datei geöffnet ist.  Wenn eine Datei geöffnet ist, wird <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> festgelegt ist, um `true`ist, andernfalls ist festgelegt ist, dass `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)
