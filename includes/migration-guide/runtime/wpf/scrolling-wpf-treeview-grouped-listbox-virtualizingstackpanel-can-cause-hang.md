---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497823"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Das Scrollen für ein WPF-TreeView-Steuerelement oder ein gruppiertes ListBox-Steuerelement in VirtualizingStackPanel kann zu einem Absturz führen

#### <a name="details"></a>Details

Das Scrollen für ein WPF-<xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Element in .NET Framework 4.5 in einem virtualisierten StackPanel-Element kann zu einem Absturz führen, wenn im Anzeigebereich Ränder vorhanden sind (z.B. zwischen den Elementen in <xref:System.Windows.Controls.TreeView?displayProperty=fullName> oder für ein ItemsPresenter-Element). Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.

#### <a name="suggestion"></a>Vorschlag

Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ können Ränder aus Ansichtsauflistungen (z.B. mehreren <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Elementen) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
