---
ms.openlocfilehash: 00ffc782c9a15c0d88f797f52372b4658706b350
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620424"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|
