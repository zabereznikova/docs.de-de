---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497693"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>„GlyphRun.ComputeInkBoundingBox()“ und „FormattedText.Extent“ geben ab .NET Framework 4.5 verschiedene Werte zurück

#### <a name="details"></a>Details

Es wurden in .NET Framework 4.5 Verbesserungen an <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> und <xref:System.Windows.Media.FormattedText.Extent> vorgenommen, um Probleme zu beheben, bei denen Felder für die darin enthaltenen Glyphen in .NET Framework 4.0 zu klein waren. Aus diesem Grund sind einige Begrenzungsrahmen in .NET Framework 4.5 größer, sodass sich geringfügige Unterschiede beim Layout der Benutzeroberfläche ergeben.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass einige Begrenzungsrahmen für Glyphen vergrößert wurden. Diese Änderungen verbessert in der Regel die Darstellung und das Testen von Feldtreffern, aber wenn das ältere Verhalten (vor .NET 4.5) gewünscht wird, kann es durch Hinzufügen des folgenden Eintrags zur Datei „app.config“ aktiviert werden:<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
