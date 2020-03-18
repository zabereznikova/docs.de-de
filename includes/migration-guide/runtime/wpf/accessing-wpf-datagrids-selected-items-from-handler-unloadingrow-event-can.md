---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858485"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>Der Zugriff auf die ausgewählten Elemente eines WPF-DataGrid-Steuerelements über einen Handler des UnloadingRow-Ereignisses kann eine NullReferenceException auslösen

|   |   |
|---|---|
|Details|Aufgrund eines Fehlers in .NET Framework 4.5 können Ereignishandler für <xref:System.Windows.Controls.DataGrid>-Ereignisse, die das Entfernen einer Zeile umfassen, eine <xref:System.NullReferenceException?displayProperty=name> auslösen, die ausgelöst werden soll, wenn auf die <xref:System.Windows.Controls.DataGrid>- oder <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name>-Eigenschaft von <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> zugegriffen wird.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
