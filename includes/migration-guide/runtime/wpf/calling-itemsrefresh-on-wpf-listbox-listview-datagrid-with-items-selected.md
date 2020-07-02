---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620423"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Das Aufrufen von Items.Refresh für die WPF-Steuerelemente ListBox, ListView oder DataGrid mit ausgewählten Einträgen kann dazu führen, dass im Element doppelte Einträge angezeigt werden.

#### <a name="details"></a>Details

In .NET Framework 4.5 kann der Aufruf von „ListBox.Items.Refresh“ mit ausgewählten Einträgen über Code dazu führen, dass die in <xref:System.Windows.Controls.ListBox?displayProperty=fullName> ausgewählten Einträge in der Liste doppelt vorkommen. Bei <xref:System.Windows.Controls.ListView?displayProperty=fullName> und <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> tritt ein ähnliches Problem auf. Dieses Problem wurde in .NET Framework 4.6 behoben.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem kann dadurch umgangen werden, dass die Auswahl der Einträge programmgesteuert aufgehoben wird, bevor <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> aufgerufen wird. Nachdem der Aufruf abgeschlossen ist, werden die Einträge erneut ausgewählt. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
