### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath löst NullReferenceException aus

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 löst die Laufzeit <code>T:System.NullReferenceException</code> aus, wenn ein <code>P:System.Web.HttpRuntime.AppDomainAppPath</code>-Wert abgerufen wird, der NULL-Zeichen enthält. In .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit eine <code>T:System.ArgumentNullException</code> aus.|
|Vorschlag|Sie können mit einer der folgenden Möglichkeiten auf diese Änderung reagieren:<ul><li>Behandeln Sie die <code>T:System.NullReferenceException</code>, wenn Ihre Anwendung in .NET Framework 4.6.2 ausgeführt wird.</li><li>Führen Sie ein Upgrade auf .NET Framework 4.7 durch, sodass das vorherige Verhalten wiederhergestellt und eine <code>T:System.ArgumentNullException</code> ausgelöst wird.</li></ul>|
|Bereich|Microsoft Edge|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|

