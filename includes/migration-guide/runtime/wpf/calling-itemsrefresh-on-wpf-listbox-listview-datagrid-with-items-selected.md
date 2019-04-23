---
ms.openlocfilehash: de73145273ad5aa5c19de55525417cfc3305b86d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235234"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Das Aufrufen von Items.Refresh für die WPF-Steuerelemente ListBox, ListView oder DataGrid mit ausgewählten Einträgen kann dazu führen, dass im Element doppelte Einträge angezeigt werden.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 kann der Aufruf von „ListBox.Items.Refresh“ mit ausgewählten Einträgen über Code dazu führen, dass die in <xref:System.Windows.Controls.ListBox?displayProperty=name> ausgewählten Einträge in der Liste doppelt vorkommen. Bei <xref:System.Windows.Controls.ListView?displayProperty=name> und <xref:System.Windows.Controls.DataGrid?displayProperty=name> tritt ein ähnliches Problem auf. Dieses Problem wurde in .NET Framework 4.6 behoben.|
|Vorschlag|Dieses Problem kann dadurch umgangen werden, dass die Auswahl der Einträge programmgesteuert aufgehoben wird, bevor <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> aufgerufen wird. Nachdem der Aufruf abgeschlossen ist, werden die Einträge erneut ausgewählt. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
