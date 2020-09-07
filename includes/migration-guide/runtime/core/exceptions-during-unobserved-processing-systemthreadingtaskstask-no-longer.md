---
ms.openlocfilehash: bae211e5684dc1fbbb1d7e69c928e37c1c532096
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497394"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="5ebdf-101">Ausnahmen während der nicht überwachten Verarbeitung in System.Threading.Tasks.Task werden nicht mehr an den Finalizerthread weitergegeben</span><span class="sxs-lookup"><span data-stu-id="5ebdf-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

#### <a name="details"></a><span data-ttu-id="5ebdf-102">Details</span><span class="sxs-lookup"><span data-stu-id="5ebdf-102">Details</span></span>

<span data-ttu-id="5ebdf-103">Da die <xref:System.Threading.Tasks.Task?displayProperty=fullName>-Klasse einen asynchronen Vorgang darstellt, fängt sie alle nicht schwerwiegenden Ausnahmen ab, die während einer asynchronen Verarbeitung auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ebdf-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=fullName> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="5ebdf-104">Wenn eine Ausnahme in .NET Framework 4.5 nicht überwacht wird und der Code nie auf die Aufgabe wartet, wird die Ausnahme nicht mehr im Finalizer-Thread weitergegeben und führt dazu, dass der Prozess während der Garbage Collection abstürzt.</span><span class="sxs-lookup"><span data-stu-id="5ebdf-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="5ebdf-105">Diese Änderung erhöht die Zuverlässigkeit von Anwendungen, die mithilfe der Task-Klasse nicht überwachte asynchrone Verarbeitungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ebdf-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5ebdf-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="5ebdf-106">Suggestion</span></span>

<span data-ttu-id="5ebdf-107">Wenn eine App von nicht überwachten asynchronen Ausnahmen abhängt, die an den Finalizer-Thread weitergegeben werden, kann das vorherige Verhalten wiederhergestellt werden, indem ein entsprechender Handler für das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>-Ereignis bereitgestellt oder ein [Runtimekonfigurationselement](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5ebdf-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>

| <span data-ttu-id="5ebdf-108">name</span><span class="sxs-lookup"><span data-stu-id="5ebdf-108">Name</span></span>    | <span data-ttu-id="5ebdf-109">Wert</span><span class="sxs-lookup"><span data-stu-id="5ebdf-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5ebdf-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="5ebdf-110">Scope</span></span>   |<span data-ttu-id="5ebdf-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5ebdf-111">Edge</span></span>|
|<span data-ttu-id="5ebdf-112">Version</span><span class="sxs-lookup"><span data-stu-id="5ebdf-112">Version</span></span>|<span data-ttu-id="5ebdf-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5ebdf-113">4.5</span></span>|
|<span data-ttu-id="5ebdf-114">Typ</span><span class="sxs-lookup"><span data-stu-id="5ebdf-114">Type</span></span>|<span data-ttu-id="5ebdf-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5ebdf-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5ebdf-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5ebdf-116">Affected APIs</span></span>

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
