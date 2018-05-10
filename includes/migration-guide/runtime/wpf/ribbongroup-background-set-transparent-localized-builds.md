### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt

|   |   |
|---|---|
|Details|Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte. Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.|
|Vorschlag|Upgrade auf .NET Framework 4.7|
|Bereich|Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit|

