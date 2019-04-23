---
ms.openlocfilehash: 0887379fb23e9e66c6cc55a3774545162634c3f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804007"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Das Scrollen für ein WPF-TreeView-Steuerelement oder ein gruppiertes ListBox-Steuerelement in VirtualizingStackPanel kann zu einem Absturz führen

|   |   |
|---|---|
|Details|Das Scrollen für ein WPF-<xref:System.Windows.Controls.TreeView?displayProperty=name>-Element in .NET Framework 4.5 in einem virtualisierten StackPanel-Element kann zu einem Absturz führen, wenn im Anzeigebereich Ränder vorhanden sind (z.B. zwischen den Elementen in <xref:System.Windows.Controls.TreeView?displayProperty=name> oder für ein ItemsPresenter-Element). Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.|
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ können Ränder aus Ansichtsauflistungen (z.B. mehreren <xref:System.Windows.Controls.TreeView?displayProperty=name>-Elementen) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
