---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614553"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException im Ausnahmebehandlungscode von ImageSourceConverter.ConvertFrom

#### <a name="details"></a>Details

Ein Fehler im Ausnahmebehandlungscode für <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> löste einen inkorrekten <xref:System.NullReferenceException?displayProperty=fullName> anstelle der beabsichtigten Ausnahme (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> oder <xref:System.IO.FileNotFoundException?displayProperty=fullName>) aus. Diese Änderung korrigiert diesen Fehler, damit die Methode nun die richtige Ausnahme auslöst. <p/>In der Standardeinstellung lösen Anwendungen mit dem Ziel .NET Framework 4.6.2 und früher der Kompatibilität wegen weiterhin <xref:System.NullReferenceException?displayProperty=fullName> aus. Entwickler, die .NET Framework 4.7 und höher anzielen, sollten die richtigen Ausnahmen angezeigt bekommen.

#### <a name="suggestion"></a>Vorschlag

Entwickler, die wieder <xref:System.NullReferenceException?displayProperty=fullName> erhalten möchten, wenn Sie .NET Framework 4.7 oder höher als Zielplattform verwenden, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen oder die entsprechenden Angaben zusammenführen:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
