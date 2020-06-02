---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144479"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist

Ab .NET 5.0 löst <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> eine <xref:System.InvalidOperationException> anstelle einer <xref:System.ArgumentException> aus, wenn der Indikatorensatz bereits vorhanden ist.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework und .NET Core 1.0 bis 3.1 können Sie eine Instanz des Indikatorensatzes erstellen, indem Sie <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen. Wenn der Indikatorensatz jedoch bereits vorhanden ist, löst die Methode eine <xref:System.ArgumentException>-Ausnahme aus.

Wenn Sie in .NET 5.0 und höheren Versionen <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> aufrufen und der Indikatorensatz vorhanden ist, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Vorschau 5

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie beim Aufrufen von <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> <xref:System.ArgumentException>-Ausnahmen in Ihrer App abfangen, sollten Sie auch <xref:System.InvalidOperationException>-Ausnahmen abfangen.

> [!NOTE]
> Das Abfangen von <xref:System.ArgumentException>-Ausnahmen wird nicht empfohlen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
