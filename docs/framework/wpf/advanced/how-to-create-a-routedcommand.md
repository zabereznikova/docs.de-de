---
title: "Gewusst wie: Erstellen eines RoutedCommand | Microsoft Docs"
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
  - "Klassen, RoutedCommand, Erstellen"
  - "Erstellen, RoutedCommand-Klasse"
  - "RoutedCommand-Klasse, Erstellen"
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen eines RoutedCommand
In diesem Beispiel wird gezeigt, wie ein benutzerdefinierter <xref:System.Windows.Input.RoutedCommand> erstellt und durch das Erstellen eines <xref:System.Windows.Input.ExecutedRoutedEventHandler> und eines <xref:System.Windows.Input.CanExecuteRoutedEventHandler> und das Anfügen von beiden an eine <xref:System.Windows.Input.CommandBinding> implementiert wird.  Weitere Informationen über Befehle finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Beispiel  
 Der erste Schritt bei der Erstellung eines <xref:System.Windows.Input.RoutedCommand> besteht darin, den Befehl zu definieren und zu instanziieren.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Um den Befehl in einer Anwendung verwenden zu können, müssen Ereignishandler erstellt werden, die die Funktionen des Befehls definieren.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Anschließend wird eine <xref:System.Windows.Input.CommandBinding> erstellt, die den Befehl den Ereignishandlern zuordnet.  Die <xref:System.Windows.Input.CommandBinding> wird auf einem bestimmten Objekt erstellt.  Dieses Objekt definiert den Bereich der <xref:System.Windows.Input.CommandBinding> in der Elementstruktur.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Im letzten Schritt wird der Befehl aufgerufen.  Eine Möglichkeit, einen Befehl aufzurufen, besteht darin, ihn einer <xref:System.Windows.Input.ICommandSource> wie einem <xref:System.Windows.Controls.Button> zuzuordnen.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Wenn auf die Schaltfläche geklickt wird, wird die <xref:System.Windows.Input.RoutedCommand.Execute%2A>\-Methode auf dem benutzerdefinierten <xref:System.Windows.Input.RoutedCommand> aufgerufen.  <xref:System.Windows.Input.RoutedCommand> löst die Routingereignisse <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> aus.  Diese Ereignisse durchlaufen die Elementstruktur auf der Suche nach einer <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl.  Wenn eine <xref:System.Windows.Input.CommandBinding> gefunden wird, wird der <xref:System.Windows.Input.ExecutedRoutedEventHandler> aufgerufen, der <xref:System.Windows.Input.CommandBinding> zugeordnet ist.  
  
## Siehe auch  
 <xref:System.Windows.Input.RoutedCommand>   
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)