---
title: 'Vorgehensweise: Erstellen eines RoutedCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776479"
---
# <a name="how-to-create-a-routedcommand"></a>Vorgehensweise: Erstellen eines RoutedCommand
In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.Windows.Input.RoutedCommand> und zum Implementieren von benutzerdefinierten Befehls durch das Erstellen einer <xref:System.Windows.Input.ExecutedRoutedEventHandler> und ein <xref:System.Windows.Input.CanExecuteRoutedEventHandler> und zum Anfügen von einer <xref:System.Windows.Input.CommandBinding>.  Weitere Informationen über Befehle finden Sie unter den [Befehlsübersicht](commanding-overview.md).  
  
## <a name="example"></a>Beispiel  
 Der erste Schritt beim Erstellen einer <xref:System.Windows.Input.RoutedCommand> definieren Sie den Befehl und zu instanziieren ist.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Um den Befehl in einer Anwendung verwenden zu können, müssen Ereignishandler definieren Sie die Funktionsweise des Befehls erstellt werden  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Als Nächstes wird ein <xref:System.Windows.Input.CommandBinding> wird erstellt, die der Befehl den Ereignishandlern verknüpft. Die <xref:System.Windows.Input.CommandBinding> auf ein bestimmtes Objekt erstellt wird.  Dieses Objekt definiert den Bereich der <xref:System.Windows.Input.CommandBinding> in der Elementstruktur  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Der letzte Schritt ist das Aufrufen des Befehls.  Eine Möglichkeit zum Aufrufen eines Befehls ist Zuordnen einer <xref:System.Windows.Input.ICommandSource>, z. B. eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Wenn die Schaltfläche geklickt wird, die <xref:System.Windows.Input.RoutedCommand.Execute%2A> Methode für die benutzerdefinierte <xref:System.Windows.Input.RoutedCommand> aufgerufen wird.  Die <xref:System.Windows.Input.RoutedCommand> löst die <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> Routingereignisse.  Diese Ereignisse durchlaufen die Elementstruktur nach einem <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl.  Wenn eine <xref:System.Windows.Input.CommandBinding> gefunden wird, wird die <xref:System.Windows.Input.ExecutedRoutedEventHandler> zugeordneten <xref:System.Windows.Input.CommandBinding> aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Input.RoutedCommand>
- [Befehlsübersicht](commanding-overview.md)
