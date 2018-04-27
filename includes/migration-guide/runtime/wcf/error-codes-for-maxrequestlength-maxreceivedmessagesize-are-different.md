### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Die Fehlercodes für maxRequestLength oder maxReceivedMessageSize sind unterschiedlich

|   |   |
|---|---|
|Details|Meldung in WCF-Webdiensten, die in Internetinformationsdiensten (Internet Information Services, IIS) oder in ASP.NET Development Server gehostet werden und maxRequestLength (in ASP.NET) oder maxReceivedMessageSize (in WCF) überschreiten, haben verschiedene Fehlercodes. Der HTTP-Statuscode hat sich von 400 (Ungültige Anforderung) in 413 (Anforderungseinheit zu groß) geändert, und entweder die maxRequestLength- oder die maxReceivedMessageSize-Einstellung löst eine <xref:System.ServiceModel.ProtocolException?displayProperty=name>-Ausnahme aus. Dies gilt auch für Fälle, in denen der Übergangsmodus „Streamed“ ist.|
|Vorschlag|Diese Änderung erleichtert das Debuggen in Fällen, in denen die Länge der Meldung die von ASP.NET oder WCF zulässigen Limits überschreiten. Sie müssen sämtlichen Code ändern, der Verarbeitungen auf Grundlage des HTTP-Statuscodes „400“ durchführt.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

