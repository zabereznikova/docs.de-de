---
title: 'Vorgehensweise: Aktivieren eines Befehls'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: 904d5a3404b693c383731eda01e9e43b2d5126fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622064"
---
# <a name="how-to-enable-a-command"></a>Vorgehensweise: Aktivieren eines Befehls
Im folgende Beispiel wird veranschaulicht, wie Befehle in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Im Beispiel veranschaulicht das Zuordnen eine <xref:System.Windows.Input.RoutedCommand> auf eine <xref:System.Windows.Controls.Button>, erstellen eine <xref:System.Windows.Input.CommandBinding>, und erstellen Sie die Ereignishandler, die Implementierung der <xref:System.Windows.Input.RoutedCommand>.  Weitere Informationen über Befehle finden Sie unter den [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Beispiel  
 Im ersten Abschnitt des Codes erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], bestehend eine <xref:System.Windows.Controls.Button> und ein <xref:System.Windows.Controls.StackPanel>, und erstellt eine <xref:System.Windows.Input.CommandBinding> , die den Befehlshandler mit ordnet die <xref:System.Windows.Input.RoutedCommand>.  
  
 Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft der <xref:System.Windows.Controls.Button> zugeordnet ist die <xref:System.Windows.Input.ApplicationCommands.Close%2A> Befehl.  
  
 Die <xref:System.Windows.Input.CommandBinding> wird hinzugefügt, um die <xref:System.Windows.Input.CommandBindingCollection> des Stamms <xref:System.Windows.Window>. Die <xref:System.Windows.Input.CommandBinding.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> Ereignishandler angefügt, die auf diese Bindung und zugeordnete der <xref:System.Windows.Input.ApplicationCommands.Close%2A> Befehl.  
  
 Ohne die <xref:System.Windows.Input.CommandBinding> keine Befehlslogik, sondern nur einen Mechanismus zum Aufrufen des Befehls ist.  Wenn die <xref:System.Windows.Controls.Button> geklickt wird, die <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> wird ausgelöst, für das Befehlsziel, gefolgt von der <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Diese Ereignisse durchlaufen die Elementstruktur nach einem <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl.  Es ist, beachten Sie, dass da <xref:System.Windows.RoutedEvent> und aufwärts durch die Elementstruktur, Vorsicht, aus denen die <xref:System.Windows.Input.CommandBinding> wird eingefügt.   Wenn die <xref:System.Windows.Input.CommandBinding> befindet sich auf ein gleichgeordnetes Element, das Ziel des Befehls oder einen anderen Knoten, die nicht auf die Route ist die <xref:System.Windows.RoutedEvent>, <xref:System.Windows.Input.CommandBinding> wird nicht zugegriffen werden.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 Der nächste Abschnitt des Codes implementiert die <xref:System.Windows.Input.CommandManager.Executed> und <xref:System.Windows.Input.CommandBinding.CanExecute> -Ereignishandler.  
  
 Die <xref:System.Windows.Input.CommandManager.Executed> Handler Ruft eine Methode, um die geöffnete Datei zu schließen.  Die <xref:System.Windows.Input.CommandBinding.CanExecute> Handler Ruft eine Methode, um festzustellen, ob eine Datei geöffnet ist.  Wenn eine Datei geöffnet ist, ist <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> nastaven NA hodnotu `true`ist, andernfalls wird festgelegt `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Siehe auch
- [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)
