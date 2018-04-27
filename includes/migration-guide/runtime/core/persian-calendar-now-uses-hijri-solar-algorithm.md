### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Der persische Kalender verwendet jetzt den Hijri-Solaralgorithmus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 verwendet die <xref:System.Globalization.PersianCalendar?displayProperty=name>-Klasse den Hijri-Solaralgorithmus. Das Konvertieren von Datumsangaben zwischen <xref:System.Globalization.PersianCalendar?displayProperty=name> und anderen Kalendern erzeugt ab .NET Framework 4.6 für Datumsangaben vor 1800 oder nach 2023 (gregorianisch) möglicherweise ein etwas anderes Ergebnis. Darüber hinaus entspricht <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> nun <code>March 22, 0622 instead of March 21, 0622</code>.|
|Vorschlag|Beachten Sie, dass einige frühe oder späte Datumsangaben bei der Verwendung des persischen Kalenders in .NET 4.6 möglicherweise etwas anders aussehen. Speichern Sie zudem beim Serialisieren von Daten zwischen Prozessen, die möglicherweise unter verschiedenen Versionen von .NET Framework ausgeführt werden, die Daten nicht als PersionCalendar-Datumszeichenfolgen (da diese Werte abweichen können).|
|Bereich|Gering|
|Version|4.6|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|

