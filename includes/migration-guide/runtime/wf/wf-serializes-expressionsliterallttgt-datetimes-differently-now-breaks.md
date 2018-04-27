### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF serialisiert Expressions.Literal&lt;T&gt; DateTimes jetzt anders (unterbricht benutzerdefinierte XAML-Parser)

|   |   |
|---|---|
|Details|Das zugeordnete <xref:System.Windows.Markup.ValueSerializer>-Objekt konvertiert ein <xref:System.DateTime?displayProperty=name>- oder <xref:System.DateTimeOffset?displayProperty=name>-Objekt, dessen Second- und <xref:System.DateTime.Millisecond?displayProperty=name>-Komponenten (Sekunden und Millisekunden) ungleich 0 (null) sind und (für einen <xref:System.DateTime?displayProperty=name>-Wert) dessen <xref:System.DateTime.Kind>-Eigenschaft nicht angegeben ist, in eine Eigenschaftenelementsyntax anstatt in eine Zeichenfolge. Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=name>- und <xref:System.DateTimeOffset?displayProperty=name>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|
|Vorschlag|Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=name>- und <xref:System.DateTimeOffset?displayProperty=name>-Werten ein Roundtrip ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

