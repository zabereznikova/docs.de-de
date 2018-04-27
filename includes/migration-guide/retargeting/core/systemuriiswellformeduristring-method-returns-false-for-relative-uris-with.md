### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Die Methode System.Uri.IsWellFormedUriString gibt für relative URIs mit einem Doppelpunktzeichen im ersten Segment FALSE zurück

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 zeigt <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> für relative URIs mit einem <code>:</code> im ersten Segment an, dass es sich nicht um einen wohlgeformten relativen URI handelt. Dies ist eine Änderung des <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name>-Verhaltens in .NET Framework 4.0, die vorgenommen wurde, um eine Übereinstimmung mit RFC3986 sicherzustellen.|
|Vorschlag|Diese Änderung wirkt sich (wie viele andere URI-Änderungen auch) nur auf Anwendungen aus, die auf .NET Framework 4.5 (oder höher) ausgerichtet sind. Damit Sie weiterhin das alte Verhalten verwenden können, müssen Sie als Zielplattform für die App NET Framework 4.0 verwenden. Überprüfen Sie alternativ die URIs, bevor Sie <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> aufrufen, und suchen Sie nach <code>:</code>-Zeichen, die Sie für die Überprüfung entfernen sollten, wenn das alte Verhalten bevorzugt wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|

