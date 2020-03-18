---
ms.openlocfilehash: 1545c807e3bef675e63e14d01ab82c1131600f39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857532"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear entfernt keine Duplikate aus SelectedItems

|   |   |
|---|---|
|Details|Angenommen, ein Selektor (mit aktivierter Mehrfachauswahl) verfügt in seiner <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>-Sammlung über Duplikate, sodass das gleiche Element mehrmals angezeigt wird.  Beim Entfernen dieser Elemente aus der Datenquelle (z.B. durch Aufrufen von Items.Clear) werden sie dann nicht aus <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> entfernt. Es wird nur die erste Instanz entfernt. Darüber hinaus kann die anschließende Verwendung von <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> (z.B. SelectedItems.Clear()) Probleme wie <xref:System.ArgumentException?displayProperty=name> verursachen, da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> Elemente enthält, die sich nicht mehr in der Datenquelle befinden.|
|Vorschlag|Führen Sie nach Möglichkeit ein Upgrade auf .NET 4.6.2 durch.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
