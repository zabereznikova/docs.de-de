---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497149"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear entfernt keine Duplikate aus SelectedItems

#### <a name="details"></a>Details

Angenommen, ein Selektor (mit aktivierter Mehrfachauswahl) verfügt in seiner <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>-Sammlung über Duplikate, sodass das gleiche Element mehrmals angezeigt wird.  Beim Entfernen dieser Elemente aus der Datenquelle (z.B. durch Aufrufen von Items.Clear) werden sie dann nicht aus <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> entfernt. Es wird nur die erste Instanz entfernt. Darüber hinaus kann die anschließende Verwendung von <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (z.B. SelectedItems.Clear()) Probleme wie <xref:System.ArgumentException?displayProperty=fullName> verursachen, da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> Elemente enthält, die sich nicht mehr in der Datenquelle befinden.

#### <a name="suggestion"></a>Vorschlag

Führen Sie nach Möglichkeit ein Upgrade auf .NET 4.6.2 durch.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
