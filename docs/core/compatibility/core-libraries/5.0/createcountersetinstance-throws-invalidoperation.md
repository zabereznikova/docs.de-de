---
title: 'Breaking Change: CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den CounterSet.CreateCounterSetInstance eine andere Ausnahme auslöst, wenn der Zähler bereits vorhanden ist.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759487"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="41a2a-103">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="41a2a-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="41a2a-104">Ab .NET 5.0 löst <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> eine <xref:System.InvalidOperationException> anstelle einer <xref:System.ArgumentException> aus, wenn der Indikatorensatz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="41a2a-104">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="41a2a-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="41a2a-105">Change description</span></span>

<span data-ttu-id="41a2a-106">In .NET Framework und .NET Core 1.0 bis 3.1 können Sie eine Instanz des Indikatorensatzes erstellen, indem Sie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="41a2a-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="41a2a-107">Wenn der Indikatorensatz jedoch bereits vorhanden ist, löst die Methode eine <xref:System.ArgumentException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="41a2a-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="41a2a-108">Wenn Sie in .NET 5.0 und höheren Versionen <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen und der Indikatorensatz vorhanden ist, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="41a2a-108">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="41a2a-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="41a2a-109">Version introduced</span></span>

<span data-ttu-id="41a2a-110">5.0</span><span class="sxs-lookup"><span data-stu-id="41a2a-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="41a2a-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="41a2a-111">Recommended action</span></span>

<span data-ttu-id="41a2a-112">Wenn Sie beim Aufrufen von <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> <xref:System.ArgumentException>-Ausnahmen in Ihrer App abfangen, sollten Sie auch <xref:System.InvalidOperationException>-Ausnahmen abfangen.</span><span class="sxs-lookup"><span data-stu-id="41a2a-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="41a2a-113">Das Abfangen von <xref:System.ArgumentException>-Ausnahmen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="41a2a-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="41a2a-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="41a2a-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
