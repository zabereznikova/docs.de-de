---
ms.openlocfilehash: a14395895c6be586c862d1b49aa6bf6669e4203a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68238034"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Das Aufrufen von Items.Refresh für die WPF-Steuerelemente ListBox, ListView oder DataGrid mit ausgewählten Einträgen kann dazu führen, dass im Element doppelte Einträge angezeigt werden.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 kann der Aufruf von „ListBox.Items.Refresh“ mit ausgewählten Einträgen über Code dazu führen, dass die in <xref:System.Windows.Controls.ListBox?displayProperty=name> ausgewählten Einträge in der Liste doppelt vorkommen. Bei <xref:System.Windows.Controls.ListView?displayProperty=name> und <xref:System.Windows.Controls.DataGrid?displayProperty=name> tritt ein ähnliches Problem auf. Dieses Problem wurde in .NET Framework 4.6 behoben.|
|Vorschlag|Dieses Problem kann dadurch umgangen werden, dass die Auswahl der Einträge programmgesteuert aufgehoben wird, bevor <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> aufgerufen wird. Nachdem der Aufruf abgeschlossen ist, werden die Einträge erneut ausgewählt. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
