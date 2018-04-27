### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt

|   |   |
|---|---|
|Details|Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.|
|Vorschlag|Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert. Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

