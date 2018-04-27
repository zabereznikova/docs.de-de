### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode und WebUtility.HtmlDecode führen für die BMP eine ordnungsgemäße Roundtripkonvertierung durch

|   |   |
|---|---|
|Details|Bei Anwendungen mit der Zielplattform .NET Framework 4.5 wird für Zeichen, die sich außerhalb der Basic Multilingual Plane (BMP) befinden, eine erfolgreiche Roundtripkonvertierung durchgeführt, wenn sie an die <xref:System.Net.WebUtility.HtmlDecode(System.String)>-Methoden übergeben werden.|
|Vorschlag|Diese Änderung sollte keine Auswirkung auf aktuelle Anwendungen haben. Wenn Sie jedoch das ursprüngliche Verhalten wiederherstellen möchten, legen Sie das Attribut <code>targetFramework</code> des Elements <code>&lt;httpRuntime&gt;</code> auf eine andere Zeichenfolge als &quot;4.5&quot; fest. Sie können die <code>unicodeEncodingConformance</code>- und <code>unicodeDecodingConformance</code>-Attribute des <code>&lt;webUtility&gt;</code>-Konfigurationselements auch festlegen, um dieses Verhalten unabhängig von der Zielversion von .NET Framework zu steuern.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|

