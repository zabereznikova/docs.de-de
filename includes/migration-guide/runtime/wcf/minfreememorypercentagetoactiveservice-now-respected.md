### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService wird jetzt eingehalten

|   |   |
|---|---|
|Details|Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Sie dient dazu, <xref:System.OutOfMemoryException?displayProperty=name>-Ausnahmen zu verhindern. In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung. In .NET Framework 4.5.1 wird die Einstellung beobachtet.|
|Vorschlag|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|

