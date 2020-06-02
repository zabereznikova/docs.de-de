---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144479"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="3d544-101">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="3d544-101">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="3d544-102">Ab .NET 5.0 löst <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> eine <xref:System.InvalidOperationException> anstelle einer <xref:System.ArgumentException> aus, wenn der Indikatorensatz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3d544-102">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3d544-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3d544-103">Change description</span></span>

<span data-ttu-id="3d544-104">In .NET Framework und .NET Core 1.0 bis 3.1 können Sie eine Instanz des Indikatorensatzes erstellen, indem Sie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3d544-104">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="3d544-105">Wenn der Indikatorensatz jedoch bereits vorhanden ist, löst die Methode eine <xref:System.ArgumentException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3d544-105">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="3d544-106">Wenn Sie in .NET 5.0 und höheren Versionen <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen und der Indikatorensatz vorhanden ist, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3d544-106">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3d544-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3d544-107">Version introduced</span></span>

<span data-ttu-id="3d544-108">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="3d544-108">5.0 Preview 5</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3d544-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3d544-109">Recommended action</span></span>

<span data-ttu-id="3d544-110">Wenn Sie beim Aufrufen von <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> <xref:System.ArgumentException>-Ausnahmen in Ihrer App abfangen, sollten Sie auch <xref:System.InvalidOperationException>-Ausnahmen abfangen.</span><span class="sxs-lookup"><span data-stu-id="3d544-110">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="3d544-111">Das Abfangen von <xref:System.ArgumentException>-Ausnahmen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3d544-111">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

#### <a name="category"></a><span data-ttu-id="3d544-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3d544-112">Category</span></span>

<span data-ttu-id="3d544-113">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="3d544-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3d544-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3d544-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
