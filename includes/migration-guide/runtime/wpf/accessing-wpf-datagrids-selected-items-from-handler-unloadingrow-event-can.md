---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620436"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>Der Zugriff auf die ausgewählten Elemente eines WPF-DataGrid-Steuerelements über einen Handler des UnloadingRow-Ereignisses kann eine NullReferenceException auslösen

#### <a name="details"></a>Details

Aufgrund eines Fehlers in .NET Framework 4.5 können Ereignishandler für <xref:System.Windows.Controls.DataGrid>-Ereignisse, die das Entfernen einer Zeile umfassen, eine <xref:System.NullReferenceException?displayProperty=fullName> auslösen, die ausgelöst werden soll, wenn auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName>- oder <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>-Eigenschaft von <xref:System.Windows.Controls.DataGrid> zugegriffen wird.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
