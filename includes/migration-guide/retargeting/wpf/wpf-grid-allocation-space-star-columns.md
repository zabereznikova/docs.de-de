---
ms.openlocfilehash: 3709b9e694011666cebcb0ae09fbc838f65967af
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614564"
---
### <a name="wpf-grid-allocation-of-space-to-star-columns"></a>Platzvergabe im Raster für -Spalten

#### <a name="details"></a>Details

Ab .NET Framework 4.7 ersetzt WPF den Algorithmus, den <xref:System.Windows.Controls.Grid> verwendet, um Platz für \*-Spalten zuzuweisen. Dadurch wird die den \*-Spalten zugewiesene tatsächliche Breite unter den folgenden Umständen geändert:

- Wenn mindestens eine \*-Spalte außerdem eine Minimal- oder Maximalbreite aufweist, die die proportionale Zuweisung für die betreffende Spalte außer Kraft setzt. (Die Minimalbreite kann aus einer expliziten MinWidth-Deklaration oder aus einem impliziten Minimalwert abgeleitet werden, der sich aus dem Spalteninhalt ergibt. Die maximale Breite kann nur explizit aus einer MaxWidth-Deklaration definiert werden.)
- Wenn eine oder mehrere \*-Spalten eine extrem große \*-Gewichtung deklarieren, größer als 10^298.
- Wenn die \*-Gewichtungen ausreichend verschieden sind, um zu Gleitkommainstabilität zu führen (Überlauf, Unterlauf, Genauigkeitsverlust).
- Wenn Layoutglättung aktiviert ist und der effektive DPI-Wert der Anzeige ausreichend hoch ist.
In den beiden ersten Fällen können sich die vom neuen Algorithmus erzeugten Breiten erheblich von den durch den alten Algorithmus erzeugten unterscheiden; im letzten Fall beträgt der Unterschied höchstens ein oder zwei Pixel.<p/>Der neue Algorithmus behebt mehrere Probleme, die beim alten Algorithmus auftreten:

- Die Gesamtzuweisung an Spalten kann die Breite des Rasters überschreiten. Dies kann beim Zuweisen von Platz an eine Spalte geschehen, deren proportionaler Anteil geringer als ihre Mindestgröße ist. Der Algorithmus weist die Mindestgröße zu, wodurch der für andere Spalten verfügbare Platz verringert wird. Wenn keine zuzuweisenden \*-Spalten mehr vorhanden sind, ist die Gesamtzuweisung zu groß.
- Die Gesamtzuweisung kann die Breite des Rasters unterschreiten. Dies ist das umgekehrte Problem zu Nr. 1, das beim Zuweisen zu einer Spalte auftritt, deren proportionaler Anteil größer als ihre Maximalgröße ist, wenn keine \*-Spalten zum Ausgleich des Über- oder Untermaßes vorhanden sind.
- Zwei \*-Spalten können Zuweisungen erhalten, die nicht proportional zu ihren \*-Gewichtungen sind. Dies ist eine mildere Version von Nr. 1/Nr. 2, die beim Zuweisen zu den \*-Spalten A, B und C (in dieser Reihenfolge) auftritt, wobei der proportionale Anteil von B gegen deren Min- oder Max-Bedingung verstößt. Wie oben ändert sich dadurch der für Spalte C zur Verfügung stehende Platz, die proportional eine kleinere (oder größeren) Zuweisung als A erhält.
- Spalten mit extrem hohen Gewichtungen (&gt; 10^298) werden alle behandelt, als würden sie die Gewichtung 10^298 aufweisen. Proportionale Unterschiede zwischen ihnen (und zwischen Spalten mit erheblich kleineren Gewichtungen) werden nicht berücksichtigt.
- Spalten mit der Gewichtung unendlich werden nicht ordnungsgemäß behandelt. [Tatsächlich lässt sich die Gewichtung nicht auf unendlich festlegen, aber das ist eine künstliche Einschränkung. Der Zuweisungscode hat versucht, das Problem zu behandeln, dabei aber versagt.]
- Mehrere kleinere Probleme beim Vermeiden von Überlauf, Unterlauf, Genauigkeitsverlust und ähnlichen Gleitkommaproblemen.
- Anpassungen für Layoutglättung sind bei ausreichend hohem DPI fehlerhaft.
Der neue Algorithmus erzeugt Ergebnisse, die den folgenden Kriterien genügen:<p/>A. Die einer *-Spalte zugewiesene Breite ist niemals kleiner als ihre Mindestbreite oder größer als ihre Maximalbreite.<br/>B. Jede <em>-Spalte, der nicht ihre Mindest- oder Maximalbreite zugewiesen wird, wird eine Breite zugewiesen, die proportional zu ihrer <em>-Gewichtung ist. Genauer gesagt, wenn zwei Spalten die Breite x</em> bzw. y</em> zugewiesen werden und keine der beiden Spalten ihre Minimal- oder Maximalbreite erhält, stehen die den Spalten zugewiesenen tatsächlichen Breiten v und w im gleichen Verhältnis: v / w == x / y.<br/>C. Die Gesamtbreite, die den &quot;proportionalen&quot; \*-Spalten zugewiesen wird, entspricht dem verfügbaren Platz nach der Zuweisung an die Spalten, die Bedingungen unterliegen (feste Spalten, Spalten mit automatischer Breite und \*-Spalten, denen die Minimal- oder Maximalbreite zugewiesen wird). Diese kann Null sein, beispielsweise, wenn die Summe der Mindestbreiten die zur Verfügung stehende Breite des Rasters überschreitet.<br/>D. Alle diese Anweisungen müssen im Hinblick auf das &quot;ideale&quot; Layout interpretiert werden. Wenn Layoutglättung aktiviert ist, können die tatsächlichen Breiten um bis zu ein Pixel von den idealen Breiten abweichen.<br/>Der alte Algorithmus berücksichtigte in den oben dargestellten Fällen (A), nicht jedoch die anderen Kriterien.<p/>Alle Aussagen über Spalten und Breiten in diesem Artikel gelten ebenso für Zeilen und Höhen.

#### <a name="suggestion"></a>Vorschlag

Standardmäßig verwenden Apps mit einer .NET Framework-Zielplattform ab .NET Framework 4.7 den neuen Algorithmus, während Apps mit der Zielplattform .NET Framework 4.6.2 oder früher den alten Algorithmus verwenden.<p/>Um die Standardeinstellung außer Kraft zu setzen, verwenden Sie die folgenden Konfigurationseinstellung:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Der Wert `true` legt den alten Algorithmus fest, `false` den neuen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7         |
| Typ    | Neuzuweisung |
