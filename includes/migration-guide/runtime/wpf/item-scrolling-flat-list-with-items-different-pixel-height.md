---
ms.openlocfilehash: 3a82822aae281ea7e873ba649f05b1d68686ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997621"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Elementscrolling durch eine flache Liste mit Elementen mit unterschiedlicher Pixelhöhe

|   |   |
|---|---|
|Details|Wenn ein <xref:System.Windows.Controls.ItemsControl?displayProperty=name>-Element eine Sammlung mithilfe von Virtualisierung (<code>IsVirtualizing=true</code>) und Elementscrolling (<code>ScrollUnit=Item</code>) anzeigt, und wenn das Steuerelement gescrollt wird, um ein Element anzuzeigen, dessen Größe in Pixeln sich von dessen Nachbarn unterscheidet, durchläuft <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> alle Elemente in der Sammlung. Die Benutzeroberfläche reagiert während dieser Iteration nicht. Wenn die Sammlung groß ist, kann dies als Absturz wahrgenommen werden. Die Iteration tritt auch in anderen Fällen und selbst in früheren .NET Framework-Releases auf. Sie tritt z.B. beim Scrollen von Pixeln (<code>ScrollUnit=Pixel</code>) auf, nachdem ein Element mit einer anderen Pixelhöhe erkannt wurde sowie beim Elementscrolling für hierarchische Daten (wie beim <xref:System.Windows.Controls.TreeView?displayProperty=name>-Steuerelement oder einem <xref:System.Windows.Controls.ItemsControl?displayProperty=name>-Element mit aktivierter Gruppierung), nachdem bei einem Element eine andere Anzahl von Nachfolgerelementen als bei seinen Nachbarn erkannt wurde. Im Fall des Elementscrollings bei unterschiedlicher Pixelhöhe wurde die Iteration in .NET Framework 4.6.1 eingeführt, um Fehler im Layout der hierarchischen Daten zu beheben.  Dies ist für flache Datenstrukturen (ohne Hierarchie) nicht erforderlich, und .NET Framework 4.6.2 führt die Iteration in diesem Fall nicht aus.|
|Vorschlag|Wenn die Iteration in .NET Framework 4.6.1, aber nicht in früheren Releases auftritt, also wenn <xref:System.Windows.Controls.ItemsControl?displayProperty=name> das Elementscrolling in einer flachen Liste von Elementen mit unterschiedlicher Pixelhöhe durchführt, gibt es zwei Lösungen:<ol><li>.NET Framework 4.6.2 installieren</li><li>Hotfix HR 1605 für .NET Framework 4.6.1 installieren</li></ol>|
|`Scope`|Nebenversion|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
