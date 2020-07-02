---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622026"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Der Aufruf von DataGrid.CommitEdit über einen CellEditEnding-Handler verliert den Fokus

#### <a name="details"></a>Details

Wenn das <xref:System.Windows.Controls.DataGrid.CommitEdit>-Element von einem der <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName>-Ereignishandler von <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> aufgerufen, verliert <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> den Fokus.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden. Alternativ kann dies vermieden werden, indem das <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>-Element nach dem Aufruf von <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> explizit neu ausgewählt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
