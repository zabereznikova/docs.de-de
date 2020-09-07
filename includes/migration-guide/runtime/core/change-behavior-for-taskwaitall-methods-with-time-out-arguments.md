---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496465"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Änderung des Verhaltens für Task.WaitAll-Methoden mit Timeout-Argumenten

#### <a name="details"></a>Details

Das <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>-Verhalten wurde in .NET Framework 4.5 einheitlicher gestaltet. In .NET Framework 4 haben sich diese Methoden unterschiedlich verhalten. Wenn vor dem abgelaufenen Timeoutintervall eine oder mehrere Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, löste die Methode eine <xref:System.AggregateException?displayProperty=fullName>-Ausnahme aus. Wenn vor dem abgelaufenen Timeoutintervall keine Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, aber eine oder mehrere Aufgaben nach dem Methodenaufruf in diesen Zustand eingetreten waren, gab die Methode „false“ zurück.<br/><br/>In .NET Framework 4.5 geben diese Methodenüberladungen jetzt FALSE zurück, falls noch Aufgaben ausgeführt werden, wenn das Timeoutintervall abläuft, und sie lösen nur dann eine <xref:System.AggregateException?displayProperty=fullName>-Ausnahme aus, wenn eine Eingabeaufgabe abgebrochen wurde (unabhängig davon, ob dies vor oder nach dem Aufruf der Methode erfolgt ist) und keine anderen Aufgaben mehr ausgeführt werden.

#### <a name="suggestion"></a>Vorschlag

Wenn eine <xref:System.AggregateException?displayProperty=fullName> als Mittel zum Erkennen einer Aufgabe abgefangen wurde, die vor dem <xref:System.Threading.Tasks.Task.WaitAll%2A>-Aufruf abgebrochen wurde, sollte dieser Code stattdessen dieselbe Erkennung über die <xref:System.Threading.Tasks.Task.IsCanceled%2A>-Eigenschaft durchführen (Beispiel: .Any(t =&gt; t.IsCanceled)), da .NET Framework 4.6 nur in dem Fall eine Ausnahme auslöst, wenn alle erwarteten Aufgaben vor dem Timeout abgeschlossen sind.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
