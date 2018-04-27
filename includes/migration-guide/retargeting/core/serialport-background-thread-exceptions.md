### <a name="serialport-background-thread-exceptions"></a>Ausnahmen in SerialPort-Hintergrundthreads

|   |   |
|---|---|
|Details|Mit <xref:System.IO.Ports.SerialPort>-Streams erstellte Hintergrundthreads beenden den Prozess nicht mehr, wenn Ausnahmen für das Betriebssystem ausgelöst werden. In Anwendungen mit der Zielplattform .NET Framework 4.7 und früheren Versionen wird ein Prozess beendet, wenn eine Ausnahme für das Betriebssystem in einem Hintergrundthread ausgelöst wird, der mit einem <xref:System.IO.Ports.SerialPort>-Stream erstellt wurde. In Apps mit der Zielplattform .NET Framework 4.7.1 oder einer höheren Version warten Hintergrundthreads auf Betriebssystemereignisse, die im Zusammenhang mit dem aktiven seriellen Port stehen und in manchen Fällen abstürzen können, z.B. wenn der serielle Port plötzlich entfernt wird.|
|Vorschlag|Für Apps mit der Zielplattform .NET Framework 4.7.1 können Sie sich gegen die Ausnahmebehandlung entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer <code>app.config</code>-Datei hinzufügen:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.1 oder höher ausgeführt werden, können Sie die Ausnahmebehandlung verwenden, indem Sie Folgendes dem Abschnitt <code>&lt;runtime&gt;</code> der <code>app.config</code>-Datei hinzufügen:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|

