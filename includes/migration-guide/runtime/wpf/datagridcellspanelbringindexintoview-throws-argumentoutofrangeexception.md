---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497251"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
