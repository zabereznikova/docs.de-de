---
ms.openlocfilehash: fbf3c0c8f1d11f9f5997a4d1027242c4710c7107
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621796"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Elementscrolling durch eine flache Liste mit Elementen mit unterschiedlicher Pixelhöhe

#### <a name="details"></a>Details

Wenn ein <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>-Element eine Sammlung mithilfe von Virtualisierung (<code>IsVirtualizing=true</code>) und Elementscrolling (<code>ScrollUnit=Item</code>) anzeigt, und wenn das Steuerelement gescrollt wird, um ein Element anzuzeigen, dessen Größe in Pixeln sich von dessen Nachbarn unterscheidet, durchläuft <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> alle Elemente in der Sammlung. Die Benutzeroberfläche reagiert während dieser Iteration nicht. Wenn die Sammlung groß ist, kann dies als Absturz wahrgenommen werden. Die Iteration tritt auch in anderen Fällen und selbst in früheren .NET Framework-Releases auf. Sie tritt z.B. beim Scrollen von Pixeln (<code>ScrollUnit=Pixel</code>) auf, nachdem ein Element mit einer anderen Pixelhöhe erkannt wurde sowie beim Elementscrolling für hierarchische Daten (wie beim <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Steuerelement oder einem <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>-Element mit aktivierter Gruppierung), nachdem bei einem Element eine andere Anzahl von Nachfolgerelementen als bei seinen Nachbarn erkannt wurde. Im Fall des Elementscrollings bei unterschiedlicher Pixelhöhe wurde die Iteration in .NET Framework 4.6.1 eingeführt, um Fehler im Layout der hierarchischen Daten zu beheben.  Dies ist für flache Datenstrukturen (ohne Hierarchie) nicht erforderlich, und .NET Framework 4.6.2 führt die Iteration in diesem Fall nicht aus.

#### <a name="suggestion"></a>Vorschlag

Wenn die Iteration in .NET Framework 4.6.1, aber nicht in früheren Releases auftritt, also wenn <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> das Elementscrolling in einer flachen Liste von Elementen mit unterschiedlicher Pixelhöhe durchführt, gibt es zwei Lösungen:<ol><li>.NET Framework 4.6.2 installieren</li><li>Hotfix HR 1605 für .NET Framework 4.6.1 installieren</li></ol>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.1|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
