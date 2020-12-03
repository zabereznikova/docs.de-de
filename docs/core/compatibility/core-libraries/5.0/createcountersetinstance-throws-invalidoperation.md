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
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist

Ab .NET 5.0 löst <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> eine <xref:System.InvalidOperationException> anstelle einer <xref:System.ArgumentException> aus, wenn der Indikatorensatz bereits vorhanden ist.

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework und .NET Core 1.0 bis 3.1 können Sie eine Instanz des Indikatorensatzes erstellen, indem Sie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen. Wenn der Indikatorensatz jedoch bereits vorhanden ist, löst die Methode eine <xref:System.ArgumentException>-Ausnahme aus.

Wenn Sie in .NET 5.0 und höheren Versionen <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen und der Indikatorensatz vorhanden ist, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie beim Aufrufen von <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> <xref:System.ArgumentException>-Ausnahmen in Ihrer App abfangen, sollten Sie auch <xref:System.InvalidOperationException>-Ausnahmen abfangen.

> [!NOTE]
> Das Abfangen von <xref:System.ArgumentException>-Ausnahmen wird nicht empfohlen.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
