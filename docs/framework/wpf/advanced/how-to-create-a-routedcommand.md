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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109043"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="5dccc-102">Vorgehensweise: Erstellen eines RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="5dccc-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="5dccc-103">In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.Windows.Input.RoutedCommand> und zum Implementieren von benutzerdefinierten Befehls durch das Erstellen einer <xref:System.Windows.Input.ExecutedRoutedEventHandler> und ein <xref:System.Windows.Input.CanExecuteRoutedEventHandler> und zum Anfügen von einer <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="5dccc-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="5dccc-104">Weitere Informationen über Befehle finden Sie unter den [Befehlsübersicht](commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5dccc-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dccc-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dccc-105">Example</span></span>  
 <span data-ttu-id="5dccc-106">Der erste Schritt beim Erstellen einer <xref:System.Windows.Input.RoutedCommand> definieren Sie den Befehl und zu instanziieren ist.</span><span class="sxs-lookup"><span data-stu-id="5dccc-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="5dccc-107">Um den Befehl in einer Anwendung verwenden zu können, müssen Ereignishandler definieren Sie die Funktionsweise des Befehls erstellt werden</span><span class="sxs-lookup"><span data-stu-id="5dccc-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="5dccc-108">Als Nächstes wird ein <xref:System.Windows.Input.CommandBinding> wird erstellt, die der Befehl den Ereignishandlern verknüpft.</span><span class="sxs-lookup"><span data-stu-id="5dccc-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="5dccc-109">Die <xref:System.Windows.Input.CommandBinding> auf ein bestimmtes Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5dccc-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="5dccc-110">Dieses Objekt definiert den Bereich der <xref:System.Windows.Input.CommandBinding> in der Elementstruktur</span><span class="sxs-lookup"><span data-stu-id="5dccc-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="5dccc-111">Der letzte Schritt ist das Aufrufen des Befehls.</span><span class="sxs-lookup"><span data-stu-id="5dccc-111">The final step is invoking the command.</span></span>  <span data-ttu-id="5dccc-112">Eine Möglichkeit zum Aufrufen eines Befehls ist Zuordnen einer <xref:System.Windows.Input.ICommandSource>, z. B. eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5dccc-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="5dccc-113">Wenn die Schaltfläche geklickt wird, die <xref:System.Windows.Input.RoutedCommand.Execute%2A> Methode für die benutzerdefinierte <xref:System.Windows.Input.RoutedCommand> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5dccc-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="5dccc-114">Die <xref:System.Windows.Input.RoutedCommand> löst die <xref:System.Windows.Input.CommandManager.PreviewExecuted> und <xref:System.Windows.Input.CommandManager.Executed> Routingereignisse.</span><span class="sxs-lookup"><span data-stu-id="5dccc-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="5dccc-115">Diese Ereignisse durchlaufen die Elementstruktur nach einem <xref:System.Windows.Input.CommandBinding> für diesen speziellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="5dccc-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="5dccc-116">Wenn eine <xref:System.Windows.Input.CommandBinding> gefunden wird, wird die <xref:System.Windows.Input.ExecutedRoutedEventHandler> zugeordneten <xref:System.Windows.Input.CommandBinding> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5dccc-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dccc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dccc-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="5dccc-118">Befehlsübersicht</span><span class="sxs-lookup"><span data-stu-id="5dccc-118">Commanding Overview</span></span>](commanding-overview.md)
