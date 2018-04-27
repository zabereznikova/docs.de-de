### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Die WPF-Layoutglättung von Rändern wurde geändert

|   |   |
|---|---|
|Details|Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert. Auswirkungen durch diese Änderung:<ul><li>Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</li><li>Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</li><li>Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</li></ul>Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.|
|Vorschlag|Da durch diese Änderung das Clipping der rechten Seite oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config-Datei hinzugefügt wird: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>. Apps, bei denen .NET Framework 4.6 angezielt wird, aber bei denen WPF-Steuerelemente mithilfe des vorherigen Layoutalgorithmus gerendert werden sollen, können dies erreichen, indem folgende Zeile zum <code>&lt;runtime&gt;</code>-Abschnitt der app.config-Datei hinzugefügt wird: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code>.|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|

