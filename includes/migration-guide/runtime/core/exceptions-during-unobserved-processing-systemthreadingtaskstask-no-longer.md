---
ms.openlocfilehash: bae211e5684dc1fbbb1d7e69c928e37c1c532096
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497394"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Ausnahmen während der nicht überwachten Verarbeitung in System.Threading.Tasks.Task werden nicht mehr an den Finalizerthread weitergegeben

#### <a name="details"></a>Details

Da die <xref:System.Threading.Tasks.Task?displayProperty=fullName>-Klasse einen asynchronen Vorgang darstellt, fängt sie alle nicht schwerwiegenden Ausnahmen ab, die während einer asynchronen Verarbeitung auftreten. Wenn eine Ausnahme in .NET Framework 4.5 nicht überwacht wird und der Code nie auf die Aufgabe wartet, wird die Ausnahme nicht mehr im Finalizer-Thread weitergegeben und führt dazu, dass der Prozess während der Garbage Collection abstürzt. Diese Änderung erhöht die Zuverlässigkeit von Anwendungen, die mithilfe der Task-Klasse nicht überwachte asynchrone Verarbeitungen ausführen.

#### <a name="suggestion"></a>Vorschlag

Wenn eine App von nicht überwachten asynchronen Ausnahmen abhängt, die an den Finalizer-Thread weitergegeben werden, kann das vorherige Verhalten wiederhergestellt werden, indem ein entsprechender Handler für das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>-Ereignis bereitgestellt oder ein [Runtimekonfigurationselement](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) festgelegt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.Run(System.Action)`
- `M:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)`
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0},System.Threading.CancellationToken)``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}},System.Threading.CancellationToken)``
- `M:System.Threading.Tasks.Task.Start`
- `M:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)`

-->
