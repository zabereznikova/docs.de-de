---
ms.openlocfilehash: 4529d8040fc08b5290ac46abd1ef752086ea3aeb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774394"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>Neue (mehrdeutige) Dispatcher.Invoke-Überladungen können zu unterschiedlichem Verhalten führen

|   |   |
|---|---|
|Details|.NET Framework 4.5 wurde um neue Überladungen für <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> ergänzt, die einen Parameter vom Typ <xref:System.Action> enthalten. Wenn vorhandener Code erneut kompiliert wird, lösen die Compiler möglicherweise Aufrufe der Dispatcher.Invoke-Methoden, die einen <xref:System.Delegate>-Parameter aufweisen, als Aufrufe von Dispatcher.Invoke-Methoden mit einem <xref:System.Action>-Parameter auf. Wird ein Aufruf an eine Dispatcher.Invoke-Überladung mit einem <xref:System.Delegate>-Parameter als Aufruf an eine Dispatcher.Invoke-Überladung mit einem <xref:System.Action>-Parameter aufgelöst, kann es zu folgenden unterschiedlichen Verhalten kommen:<ul><li>Tritt eine Ausnahme auf, werden die <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter>- und <xref:System.Windows.Threading.Dispatcher.UnhandledException>-Ereignisse nicht ausgelöst. Stattdessen werden Ausnahmen durch das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=name>-Ereignis behandelt.</li><li>Bis der Vorgang abgeschlossen ist, werden Aufrufe an einige Member, z. B. <xref:System.Windows.Threading.DispatcherOperation.Result>, blockiert.</li></ul>|
|Vorschlag|Um Unklarheiten zu vermeiden (und mögliche Abweichungen bei der Ausnahmebehandlung oder bei blockierendem Verhalten), kann Code, der „Dispatcher.Invoke“ aufruft, ein leeres Objekt [] als zweiten Parameter an den Invoke-Aufruf übergeben, um sicherzustellen, dass nach der .NET Framework 4.0-Methodenüberladung aufgelöst wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li></ul>|
