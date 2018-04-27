### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>Die ResolveAssemblyReference-Aufgabe warnt jetzt vor Abhängigkeiten von der falschen Architektur

|   |   |
|---|---|
|Details|Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies erfolgt z. B., wenn eine App, die mit der <code>AnyCPU</code>-Option kompiliert wurde, einen x86-Verweis enthält. Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).|
|Vorschlag|Es gibt zwei Bereiche mit Auswirkungen:<ul><li>Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.</li><li>Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.</li></ul>|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Neuzuweisung|

