---
ms.openlocfilehash: 53fc2a51a7995e9b6ad43e28429313d2aea9abf1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379239"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-result-in-an-unresponsive-application"></a>Scrollvorgänge in einem WPF-TreeView-Element oder in einem gruppierten ListBox-Element in „VirtualizingStackPanel“ können dazu führen, dass eine Anwendung nicht mehr reagiert.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 können Scrollvorgänge in einem WPF-<xref:System.Windows.Controls.TreeView?displayProperty=name>-Element eines virtualisierten StackPanel-Elements dazu führen, dass eine Anwendung nicht mehr reagiert, wenn im Anzeigebereich Ränder vorhanden sind (beispielsweise zwischen den Elementen in <xref:System.Windows.Controls.TreeView?displayProperty=name> oder in einem ItemsPresenter-Element). Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.|
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ können Ränder aus Ansichtsauflistungen (z.B. mehreren <xref:System.Windows.Controls.TreeView?displayProperty=name>-Elementen) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
