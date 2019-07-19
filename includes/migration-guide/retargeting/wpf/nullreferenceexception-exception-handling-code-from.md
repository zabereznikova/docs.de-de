---
ms.openlocfilehash: 122741d13294c8b137ce48e28f0aa39c6e36265a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859106"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException im Ausnahmebehandlungscode von ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Details|Ein Fehler im Ausnahmebehandlungscode für <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> löste einen inkorrekten <xref:System.NullReferenceException?displayProperty=name> anstelle der beabsichtigten Ausnahme (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> oder <xref:System.IO.FileNotFoundException?displayProperty=name>) aus. Diese Änderung korrigiert diesen Fehler, damit die Methode nun die richtige Ausnahme auslöst. <p/>In der Standardeinstellung lösen Anwendungen mit dem Ziel .NET Framework 4.6.2 und früher der Kompatibilität wegen weiterhin <xref:System.NullReferenceException?displayProperty=name> aus. Entwickler, die .NET Framework 4.7 und höher anzielen, sollten die richtigen Ausnahmen angezeigt bekommen.|
|Vorschlag|Entwickler, die wieder <xref:System.NullReferenceException?displayProperty=name> erhalten möchten, wenn Sie .NET Framework 4.7 oder höher als Zielplattform verwenden, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen oder die entsprechenden Angaben zusammenführen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|

