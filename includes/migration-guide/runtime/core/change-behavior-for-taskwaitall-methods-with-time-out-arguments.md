---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496465"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="60d2d-101">Änderung des Verhaltens für Task.WaitAll-Methoden mit Timeout-Argumenten</span><span class="sxs-lookup"><span data-stu-id="60d2d-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

#### <a name="details"></a><span data-ttu-id="60d2d-102">Details</span><span class="sxs-lookup"><span data-stu-id="60d2d-102">Details</span></span>

<span data-ttu-id="60d2d-103">Das <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>-Verhalten wurde in .NET Framework 4.5 einheitlicher gestaltet. In .NET Framework 4 haben sich diese Methoden unterschiedlich verhalten.</span><span class="sxs-lookup"><span data-stu-id="60d2d-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="60d2d-104">Wenn vor dem abgelaufenen Timeoutintervall eine oder mehrere Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, löste die Methode eine <xref:System.AggregateException?displayProperty=fullName>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="60d2d-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="60d2d-105">Wenn vor dem abgelaufenen Timeoutintervall keine Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, aber eine oder mehrere Aufgaben nach dem Methodenaufruf in diesen Zustand eingetreten waren, gab die Methode „false“ zurück.</span><span class="sxs-lookup"><span data-stu-id="60d2d-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="60d2d-106">In .NET Framework 4.5 geben diese Methodenüberladungen jetzt FALSE zurück, falls noch Aufgaben ausgeführt werden, wenn das Timeoutintervall abläuft, und sie lösen nur dann eine <xref:System.AggregateException?displayProperty=fullName>-Ausnahme aus, wenn eine Eingabeaufgabe abgebrochen wurde (unabhängig davon, ob dies vor oder nach dem Aufruf der Methode erfolgt ist) und keine anderen Aufgaben mehr ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="60d2d-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=fullName> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="60d2d-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="60d2d-107">Suggestion</span></span>

<span data-ttu-id="60d2d-108">Wenn eine <xref:System.AggregateException?displayProperty=fullName> als Mittel zum Erkennen einer Aufgabe abgefangen wurde, die vor dem <xref:System.Threading.Tasks.Task.WaitAll%2A>-Aufruf abgebrochen wurde, sollte dieser Code stattdessen dieselbe Erkennung über die <xref:System.Threading.Tasks.Task.IsCanceled%2A>-Eigenschaft durchführen (Beispiel: .Any(t =&gt; t.IsCanceled)), da .NET Framework 4.6 nur in dem Fall eine Ausnahme auslöst, wenn alle erwarteten Aufgaben vor dem Timeout abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="60d2d-108">If an <xref:System.AggregateException?displayProperty=fullName> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>

| <span data-ttu-id="60d2d-109">name</span><span class="sxs-lookup"><span data-stu-id="60d2d-109">Name</span></span>    | <span data-ttu-id="60d2d-110">Wert</span><span class="sxs-lookup"><span data-stu-id="60d2d-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="60d2d-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="60d2d-111">Scope</span></span>   |<span data-ttu-id="60d2d-112">Gering</span><span class="sxs-lookup"><span data-stu-id="60d2d-112">Minor</span></span>|
|<span data-ttu-id="60d2d-113">Version</span><span class="sxs-lookup"><span data-stu-id="60d2d-113">Version</span></span>|<span data-ttu-id="60d2d-114">4.5</span><span class="sxs-lookup"><span data-stu-id="60d2d-114">4.5</span></span>|
|<span data-ttu-id="60d2d-115">Typ</span><span class="sxs-lookup"><span data-stu-id="60d2d-115">Type</span></span>|<span data-ttu-id="60d2d-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="60d2d-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="60d2d-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="60d2d-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
