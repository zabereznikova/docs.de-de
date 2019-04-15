---
ms.openlocfilehash: b0e6d6f228647148083d3df64e65f817dc3455d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235649"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Ausnahmen während der nicht überwachten Verarbeitung in System.Threading.Tasks.Task werden nicht mehr an den Finalizerthread weitergegeben

|   |   |
|---|---|
|Details|Da die <xref:System.Threading.Tasks.Task?displayProperty=name>-Klasse einen asynchronen Vorgang darstellt, fängt sie alle nicht schwerwiegenden Ausnahmen ab, die während einer asynchronen Verarbeitung auftreten. Wenn eine Ausnahme in .NET Framework 4.5 nicht überwacht wird und der Code nie auf die Aufgabe wartet, wird die Ausnahme nicht mehr im Finalizer-Thread weitergegeben und führt dazu, dass der Prozess während der Garbage Collection abstürzt. Diese Änderung erhöht die Zuverlässigkeit von Anwendungen, die mithilfe der Task-Klasse nicht überwachte asynchrone Verarbeitungen ausführen.|
|Vorschlag|Wenn eine App von nicht überwachten asynchronen Ausnahmen abhängt, die an den Finalizer-Thread weitergegeben werden, kann das vorherige Verhalten wiederhergestellt werden, indem ein entsprechender Handler für das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>-Ereignis bereitgestellt oder ein [Runtimekonfigurationselement](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) festgelegt wird.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
