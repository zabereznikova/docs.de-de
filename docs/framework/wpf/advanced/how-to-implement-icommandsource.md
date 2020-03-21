---
title: 'Gewusst wie: Implementieren von "ICommandSource"'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174692"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="8bb69-102">Gewusst wie: Implementieren von "ICommandSource"</span><span class="sxs-lookup"><span data-stu-id="8bb69-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="8bb69-103">In diesem Beispiel wird gezeigt, <xref:System.Windows.Input.ICommandSource>wie Sie eine Befehlsquelle erstellen, indem Sie .</span><span class="sxs-lookup"><span data-stu-id="8bb69-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="8bb69-104">Eine Befehlsquelle ist ein Objekt, das weiß, wie ein Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8bb69-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="8bb69-105">Die <xref:System.Windows.Input.ICommandSource> Schnittstelle macht drei Elemente verfügbar:</span><span class="sxs-lookup"><span data-stu-id="8bb69-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="8bb69-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: der Befehl, der aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8bb69-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="8bb69-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: ein benutzerdefinierter Datentyp, der von der Befehlsquelle an die Methode übergeben wird, die den Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8bb69-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="8bb69-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: das Objekt, auf dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8bb69-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="8bb69-109">In diesem Beispiel wird eine Klasse erstellt, <xref:System.Windows.Controls.Slider> die vom <xref:System.Windows.Input.ICommandSource> Steuerelement erbt und die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="8bb69-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="8bb69-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bb69-110">Example</span></span>

<span data-ttu-id="8bb69-111">WPF stellt eine Reihe <xref:System.Windows.Input.ICommandSource>von Klassen <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem>bereit, <xref:System.Windows.Documents.Hyperlink>die implementieren, z. B. , und .</span><span class="sxs-lookup"><span data-stu-id="8bb69-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="8bb69-112">Eine Befehlsquelle definiert, wie sie einen Befehl aufruft.</span><span class="sxs-lookup"><span data-stu-id="8bb69-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="8bb69-113">Diese Klassen rufen einen Befehl auf, wenn auf sie geklickt wird, und sie werden nur dann zu einer Befehlsquelle, wenn ihre <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8bb69-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="8bb69-114">In diesem Beispiel rufen Sie den Befehl auf, wenn der Schieberegler verschoben wird, oder genauer gesagt, wenn die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8bb69-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="8bb69-115">Im Folgenden finden Sie die Klassendefinition:</span><span class="sxs-lookup"><span data-stu-id="8bb69-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="8bb69-116">Der nächste Schritt besteht <xref:System.Windows.Input.ICommandSource> darin, die Mitglieder zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8bb69-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="8bb69-117">In diesem Beispiel werden die <xref:System.Windows.DependencyProperty> Eigenschaften als Objekte implementiert.</span><span class="sxs-lookup"><span data-stu-id="8bb69-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="8bb69-118">Dadurch können die Eigenschaften die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bb69-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="8bb69-119">Weitere Informationen zur <xref:System.Windows.DependencyProperty> Klasse finden Sie in der Übersicht über [Abhängigkeitseigenschaften](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8bb69-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="8bb69-120">Weitere Informationen zur Datenbindung finden Sie in der [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8bb69-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="8bb69-121">Hier <xref:System.Windows.Input.ICommandSource.Command%2A> wird nur die Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8bb69-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="8bb69-122">Im Folgenden <xref:System.Windows.DependencyProperty> finden Sie den Änderungsrückruf:</span><span class="sxs-lookup"><span data-stu-id="8bb69-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="8bb69-123">Der nächste Schritt besteht darin, den Befehl hinzuzufügen und zu entfernen, der der Befehlsquelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8bb69-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="8bb69-124">Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die dem vorherigen Befehl zugeordneten Ereignishandler, sofern vorhanden, zuerst entfernt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8bb69-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="8bb69-125">Der nächste Schritt besteht darin, Logik für den <xref:System.Windows.Input.ICommand.CanExecuteChanged> Handler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bb69-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="8bb69-126">Das <xref:System.Windows.Input.ICommand.CanExecuteChanged> Ereignis benachrichtigt die Befehlsquelle, dass sich die Fähigkeit des Befehls, auf dem aktuellen Befehlsziel auszuführen, möglicherweise geändert hat.</span><span class="sxs-lookup"><span data-stu-id="8bb69-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="8bb69-127">Wenn eine Befehlsquelle dieses Ereignis <xref:System.Windows.Input.ICommand.CanExecute%2A> empfängt, ruft sie in der Regel die Methode für den Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="8bb69-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="8bb69-128">Wenn der Befehl auf dem aktuellen Befehlsziel nicht ausgeführt werden kann, deaktiviert sich die Befehlsquelle in der Regel selbst.</span><span class="sxs-lookup"><span data-stu-id="8bb69-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="8bb69-129">Wenn der Befehl auf dem aktuellen Befehlsziel ausgeführt werden kann, aktiviert sich die Befehlsquelle in der Regel selbst.</span><span class="sxs-lookup"><span data-stu-id="8bb69-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="8bb69-130">Der letzte Schritt <xref:System.Windows.Input.ICommand.Execute%2A> ist die Methode.</span><span class="sxs-lookup"><span data-stu-id="8bb69-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="8bb69-131">Wenn der Befehl <xref:System.Windows.Input.RoutedCommand>ein <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> ist, wird die Methode aufgerufen. Andernfalls wird <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> die Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8bb69-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="8bb69-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8bb69-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="8bb69-133">Befehlsübersicht</span><span class="sxs-lookup"><span data-stu-id="8bb69-133">Commanding Overview</span></span>](commanding-overview.md)
