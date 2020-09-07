---
ms.openlocfilehash: 2ae17e0823ec2fa064c948d9ea7bd19cbd34cb6a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497620"
---
### <a name="horizontal-scrolling-and-virtualization"></a>Horizontales Scrollen und Virtualisierung

#### <a name="details"></a>Details

Diese Änderung betrifft <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>-Objekte mit eigener Virtualisierung in der senkrecht zur Hauptscrollrichtung stehenden Richtung (z.B. <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> mit .EnableColumnVirtualization=&quot;TRUE&quot;).  Das Ergebnis bestimmter horizontaler Scrollvorgänge wurde geändert, um Ergebnisse zu erzeugen, die intuitiver und in höheren Maß analog zu den Ergebnissen vergleichbarer vertikaler Vorgänge sind.<p/>Zu den Vorgängen gehören &quot;Bildlauf hierhin durchführen&quot; und &quot;Rechter Rand&quot;, um die Namen aus dem Menü zu verwenden, das durch Klicken mit der rechten Maustaste auf eine horizontale Scrollleiste angezeigt wird.  Beide berechnen einen Kandidatenoffset und rufen <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)> auf.<p/>Nach dem Scrollen zum neuen Offset hat sich die Definition von &quot;Hierhin&quot; oder &quot;Rechter Rand&quot; möglicherweise geändert, da die neuen entvirtualisierten Inhalte den Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> geändert haben.<p/>Vor .NET Framework 4.6.2 verwendet der Scrollvorgang einfach den Kandidatenoffset, obwohl er möglicherweise nicht mehr &quot;Hierhin&quot; oder &quot;Rechter Rand&quot; entspricht.  Dies führt zu Effekten wie einem &quot;Springen&quot; des Leistenziehpunkts, die sich am besten durch ein Beispiel veranschaulichen lassen. Nehmen Sie an, dass <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> über die Eigenschaften „ExtentWidth=1000“ und „Width=200“ verfügt.  Ein Scrollen zu &quot;Rechter Rand&quot; verwendet den Kandidatenoffset 1000 – 200 = 800.  Beim Scrollen zu diesem Offset werden neue Spalten entvirtualisiert. Nehmen Sie an, dass diese sehr breit sind, sodass sich <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> in 2000 ändert.  Das Scrollen endet bei HorizontalOffset=800, und der Ziehpunkt &quot;springt&quot; annähernd zur Mitte der Bildlaufleiste zurück – genau bei 800:2000 = 40 %.<p/>Die Änderung besteht darin, einen neuen Kandidatenoffset zu berechnen, wenn diese Situation eintritt, und es erneut zu versuchen. (Beim vertikalen Scrollen wurde dies bereits implementiert.) <p/>Die Änderung ergibt ein besser vorhersehbares und intuitiveres Verhalten für den Endbenutzer, sie kann sich aber auf jede App auswirken, die auf den genauen Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> nach einem horizontalen Scrollvorgang angewiesen ist, ob vom Endbenutzer oder durch einen expliziten Aufruf von <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)> aufgerufen.

#### <a name="suggestion"></a>Vorschlag

Eine App, die einen vorhergesagten Wert für <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> verwendet, sollte so geändert werden, dass sie nach jedem horizontalen Scrollen, durch das <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> aufgrund der Entvirtualisierung geändert werden könnte, den tatsächlichen Wert (und den Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName>) abruft.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.Primitives.IScrollInfo`

-->
