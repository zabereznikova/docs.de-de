### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage löst für eintrittsinvariante Implementierungen von IMessageFilter.PreFilterMessage keine Ausnahmen mehr aus

|   |   |
|---|---|
|Details|Vor .NET Framework 4.6.1 hat das Aufrufen von <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> mit der <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>-Methode, die wiederum <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> oder <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> (bei gleichzeitigem Aufruf von <xref:System.Windows.Forms.Application.DoEvents>) aufruft, eine <xref:System.IndexOutOfRangeException?displayProperty=name> ausgelöst. Ab Apps mit der Zielplattform NET Framework 4.6.1 wird diese Ausnahme nicht mehr ausgelöst, und es können eintrittsinvariante Filter verwendet werden, wie oben beschrieben wird.|
|Vorschlag|Beachten Sie, dass <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> keine Ausnahmen mehr für das oben beschriebene eintrittsinvariante <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>-Verhalten auslöst. Dies wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Auf .NET Framework 4.6.1 ausgerichtete Apps können diese Änderung mithilfe der [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation)-Kompatibilitätsoption ablehnen (auf ältere Framework-Versionen ausgerichtete Apps können diese Option aktivieren).|
|Bereich|Microsoft Edge|
|Version|4.6.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType></li></ul>|

