### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Änderung des Verhaltens für Task.WaitAll-Methoden mit Timeout-Argumenten

|   |   |
|---|---|
|Details|Das Task.WaitAll-Verhalten wurde in .NET 4.5 konsistenter gestaltet. In .NET Framework 4 haben diese Methoden sich unterschiedlich verhalten. Wenn vor dem abgelaufenen Timeoutintervall eine oder mehrere Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, löste die Methode eine <xref:System.AggregateException?displayProperty=name>-Ausnahme aus. Wenn vor dem abgelaufenen Timeoutintervall keine Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, aber eine oder mehrere Aufgaben nach dem Methodenaufruf in diesen Zustand eingetreten waren, gab die Methode „false“ zurück.<br/><br/>In .NET Framework 4.5 geben diese Methodenüberladungen jetzt FALSE zurück, falls noch Aufgaben ausgeführt werden, wenn das Timeoutintervall abläuft, und sie lösen nur dann eine <xref:System.AggregateException?displayProperty=name>-Ausnahme aus, wenn eine Eingabeaufgabe abgebrochen wurde (unabhängig davon, ob dies vor oder nach dem Aufruf der Methode erfolgt ist) und keine anderen Aufgaben mehr ausgeführt werden.|
|Vorschlag|Wenn eine <xref:System.AggregateException?displayProperty=name> als Mittel zum Erkennen einer Aufgabe abgefangen wurde, die vor dem WaitAll-Aufruf abgebrochen wurde, sollte dieser Code stattdessen dieselbe Erkennung über die IsCanceled-Eigenschaft durchführen (Beispiel: .Any(t =&gt; t.IsCanceled)), da .NET 4.6 nur in dem Fall eine Ausnahme auslöst, wenn alle erwarteten Aufgaben vor dem Timeout abgeschlossen sind.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|

