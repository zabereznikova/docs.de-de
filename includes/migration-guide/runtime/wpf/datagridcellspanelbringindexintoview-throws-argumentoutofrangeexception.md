---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622357"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView löst ArgumentOutOfRangeException aus

#### <a name="details"></a>Details

<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> wird asynchron ausgeführt, wenn die Spaltenvirtualisierung zwar aktiviert ist, die Spaltenbreiten aber noch nicht festgelegt wurden.  Wenn Spalten entfernt werden, bevor der asynchrone Vorgang abgeschlossen ist, kann eine <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>-Ausnahme auftreten.

#### <a name="suggestion"></a>Vorschlag

Führen Sie eine der folgenden Aktionen aus:<ol><li>Upgrade auf .NET Framework 4.7</li><li>Den neuesten Wartungspatch für .NET Framework 4.6.2 installieren</li><li>Entfernen Sie Spalten erst, wenn die asynchrone Antwort auf die <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> abgeschlossen wurde.</li></ol>

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
