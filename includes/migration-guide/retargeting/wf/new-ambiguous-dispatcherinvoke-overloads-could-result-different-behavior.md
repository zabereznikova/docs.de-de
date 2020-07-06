---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617174"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a><span data-ttu-id="58b76-101">Neue (mehrdeutige) Dispatcher.Invoke-Überladungen können zu unterschiedlichem Verhalten führen</span><span class="sxs-lookup"><span data-stu-id="58b76-101">New (ambiguous) Dispatcher.Invoke overloads could result in different behavior</span></span>

#### <a name="details"></a><span data-ttu-id="58b76-102">Details</span><span class="sxs-lookup"><span data-stu-id="58b76-102">Details</span></span>

<span data-ttu-id="58b76-103">.NET Framework 4.5 wurde um neue Überladungen für <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> ergänzt, die einen Parameter vom Typ <xref:System.Action> enthalten.</span><span class="sxs-lookup"><span data-stu-id="58b76-103">The .NET Framework 4.5 adds new overloads to <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> that include a parameter of type <xref:System.Action>.</span></span> <span data-ttu-id="58b76-104">Wenn vorhandener Code erneut kompiliert wird, lösen die Compiler möglicherweise Aufrufe der Dispatcher.Invoke-Methoden, die einen <xref:System.Delegate>-Parameter aufweisen, als Aufrufe von Dispatcher.Invoke-Methoden mit einem <xref:System.Action>-Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="58b76-104">When existing code is recompiled, compilers may resolve calls to Dispatcher.Invoke methods that have a <xref:System.Delegate> parameter as calls to Dispatcher.Invoke methods with an <xref:System.Action> parameter.</span></span> <span data-ttu-id="58b76-105">Wird ein Aufruf an eine Dispatcher.Invoke-Überladung mit einem <xref:System.Delegate>-Parameter als Aufruf an eine Dispatcher.Invoke-Überladung mit einem <xref:System.Action>-Parameter aufgelöst, kann es zu folgenden unterschiedlichen Verhalten kommen:</span><span class="sxs-lookup"><span data-stu-id="58b76-105">If a call to a Dispatcher.Invoke overload with a  <xref:System.Delegate> parameter is resolved as a call to a Dispatcher.Invoke overload with an <xref:System.Action> parameter, the following differences in behavior may occur:</span></span>

- <span data-ttu-id="58b76-106">Tritt eine Ausnahme auf, werden die <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter>- und <xref:System.Windows.Threading.Dispatcher.UnhandledException>-Ereignisse nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58b76-106">If an exception occurs, the <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> and <xref:System.Windows.Threading.Dispatcher.UnhandledException> events are not raised.</span></span> <span data-ttu-id="58b76-107">Stattdessen werden Ausnahmen durch das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>-Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="58b76-107">Instead, exceptions are handled by the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> event.</span></span>
- <span data-ttu-id="58b76-108">Bis der Vorgang abgeschlossen ist, werden Aufrufe an einige Member, z. B. <xref:System.Windows.Threading.DispatcherOperation.Result>, blockiert.</span><span class="sxs-lookup"><span data-stu-id="58b76-108">Calls to some members, such as <xref:System.Windows.Threading.DispatcherOperation.Result>, block until the operation has completed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58b76-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="58b76-109">Suggestion</span></span>

<span data-ttu-id="58b76-110">Um Unklarheiten zu vermeiden (und mögliche Abweichungen bei der Ausnahmebehandlung oder bei blockierendem Verhalten), kann Code, der „Dispatcher.Invoke“ aufruft, ein leeres Objekt [] als zweiten Parameter an den Invoke-Aufruf übergeben, um sicherzustellen, dass nach der .NET Framework 4.0-Methodenüberladung aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="58b76-110">To avoid ambiguity (and potential differences in exception handling or blocking behaviors), code calling Dispatcher.Invoke can pass an empty object[] as a second parameter to the Invoke call to be sure of resolving to the .NET Framework 4.0 method overload.</span></span>

| <span data-ttu-id="58b76-111">name</span><span class="sxs-lookup"><span data-stu-id="58b76-111">Name</span></span>    | <span data-ttu-id="58b76-112">Wert</span><span class="sxs-lookup"><span data-stu-id="58b76-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58b76-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="58b76-113">Scope</span></span>   | <span data-ttu-id="58b76-114">Gering</span><span class="sxs-lookup"><span data-stu-id="58b76-114">Minor</span></span>       |
| <span data-ttu-id="58b76-115">Version</span><span class="sxs-lookup"><span data-stu-id="58b76-115">Version</span></span> | <span data-ttu-id="58b76-116">4.5</span><span class="sxs-lookup"><span data-stu-id="58b76-116">4.5</span></span>         |
| <span data-ttu-id="58b76-117">Typ</span><span class="sxs-lookup"><span data-stu-id="58b76-117">Type</span></span>    | <span data-ttu-id="58b76-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="58b76-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="58b76-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="58b76-119">Affected APIs</span></span>

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
