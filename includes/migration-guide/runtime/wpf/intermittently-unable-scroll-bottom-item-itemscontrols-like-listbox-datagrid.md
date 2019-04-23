---
ms.openlocfilehash: 9c2ee4ba66deb7c3b33698963add2b8a7e70069f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804047"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Das Scrollen zum untersten Eintrag in ItemsControl-Steuerelementen (z.B. ListBox und DataGrid) war bei Verwendung von benutzerdefinierten DataTemplates zeitweilig nicht möglich.

|   |   |
|---|---|
|Details|In einigen Fällen verursacht ein Fehler in .NET Framework 4.5, dass ItemsControl-Steuerelemente (z.B. <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name> und <xref:System.Windows.Controls.DataGrid?displayProperty=name>) nicht zum untersten Eintrag scrollen, wenn benutzerdefinierte DataTemplates verwendet werden. Wenn der Vorgang ein zweites Mal versucht wird (nachdem wieder nach oben gescrollt wurde), funktioniert es entsprechend.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben und kann durch ein Upgrade auf diese (oder eine höhere) Version von .NET Framework vermieden werden. Alternativ können Benutzer weiterhin Scrolleisten in diesen Auflistungen ziehen, wobei sie es möglicherweise zweimal versuchen müssen, bis der Vorgang erfolgreich ausgeführt wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
