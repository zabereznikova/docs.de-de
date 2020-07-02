---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622020"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Das Scrollen zum untersten Eintrag in ItemsControl-Steuerelementen (z.B. ListBox und DataGrid) war bei Verwendung von benutzerdefinierten DataTemplates zeitweilig nicht möglich.

#### <a name="details"></a>Details

In einigen Fällen verursacht ein Fehler in .NET Framework 4.5, dass ItemsControl-Steuerelemente (z.B. <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName> und <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>) nicht zum untersten Eintrag scrollen, wenn benutzerdefinierte DataTemplates verwendet werden. Wenn der Vorgang ein zweites Mal versucht wird (nachdem wieder nach oben gescrollt wurde), funktioniert es entsprechend.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.5.2 behoben und kann durch ein Upgrade auf diese (oder eine höhere) Version von .NET Framework vermieden werden. Alternativ können Benutzer weiterhin Scrolleisten in diesen Auflistungen ziehen, wobei sie es möglicherweise zweimal versuchen müssen, bis der Vorgang erfolgreich ausgeführt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|
