---
ms.openlocfilehash: 824d75585efd40937c1a48376ec7862cba1a8fa3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235616"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException im Ausnahmebehandlungscode von ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Details|Ein Fehler im Ausnahmebehandlungscode für <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> löste einen inkorrekten <xref:System.NullReferenceException?displayProperty=name> anstelle der beabsichtigten Ausnahme (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> oder <xref:System.IO.FileNotFoundException?displayProperty=name>) aus. Diese Änderung korrigiert diesen Fehler, damit die Methode nun die richtige Ausnahme auslöst. <p/>In der Standardeinstellung lösen Anwendungen mit dem Ziel .NET Framework 4.6.2 und früher der Kompatibilität wegen weiterhin <xref:System.NullReferenceException?displayProperty=name> aus. Entwickler, die .NET Framework 4.7 und höher anzielen, sollten die richtigen Ausnahmen angezeigt bekommen.|
|Vorschlag|Entwickler, die wieder <xref:System.NullReferenceException?displayProperty=name> erhalten möchten, wenn Sie .NET Framework 4.7 oder höher als Zielplattform verwenden, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen oder die entsprechenden Angaben zusammenführen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|
