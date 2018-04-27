### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap konvertiert Symbole mit PNG-Frames erfolgreich in Bitmap-Objekte

|   |   |
|---|---|
|Details|Ab den Apps, die für .NET Framework 4.6 konzipiert sind, konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode erfolgreich Symbole mit PNG-Frames in Bitmap-Objekte. In Apps, die für .NET Framework 4.5.2 und frühere Versionen konzipiert sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das Symbolobjekt aus PNG-Frames besteht. Diese Änderung betrifft vor allem Apps, die für .NET Framework 4.6 erneut kompiliert werden und eine besondere Behandlung der <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein Symbolobjekt aus PNG-Frames besteht. Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.|
|Vorschlag|Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum <code>&lt;runtime&gt;</code>-Abschnitt Ihrer app.config-Datei hinzufügen:<pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>Wenn die Datei „app.config“ bereits das <code>AppContextSwitchOverrides</code>-Element enthält, muss der neue Wert wie folgt mit dem Attribut zusammengeführt werden:<pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|

