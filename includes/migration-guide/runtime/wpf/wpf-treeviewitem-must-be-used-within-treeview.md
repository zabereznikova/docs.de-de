---
ms.openlocfilehash: af8cb9435be078351e3430dc8ded3f7cac377948
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620496"
---
### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>WPF TreeViewItem muss in einem TreeView-Steuerelement verwendet werden

#### <a name="details"></a>Details

In .NET Framework 4.5 wurde eine Änderung eingeführt, die die Verwendung von <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName>-Elementen außerhalb eines <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Steuerelements einschränkt. Dieser Fall kann unter den folgenden Bedingungen eintreten:<ul><li>Das visuelle übergeordnete Element von <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> ist kein Panel. (Ein für <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> generiertes <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Steuerelement weist einen Panel als dessen übergeordnetes Element auf.)</li><li>Das <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName>-Element ist ein Nachfolgeelement von <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>, das als &quot;Elementhost&quot; für ein Listensteuerelement (ListBox, DataGrid, ListView usw.) fungiert. Die Virtualisierung muss nicht aktiviert werden.</li><li>Das <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>-Element wird zum Elementscrolling (<code>ScrollUnit=&quot;Item&quot;</code>) verwendet.</li><li>Jemand ruft <code>VirtualizingStackPanel.MakeVisible(v)</code> auf, um ein Element <code>v</code> in eine Ansicht zu scrollen. Dies kann auf verschiedene Arten explizit oder implizit erfolgen. Die am häufigsten verwendeten Methode ist möglicherweise einfach das Klicken auf <code>v</code>, damit es den Tastaturfokus erhält.</li><li>Die visuelle Kette des übergeordneten <code>v</code>-Elements zu <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> wird über das <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName>-Element übergeben.</li></ul>Das bedeutet, dies wird angezeigt, wenn ein <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> außerhalb von <xref:System.Windows.Controls.TreeView?displayProperty=fullName> verwendet wird und der Benutzer auf ein Nachfolgeelement von <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> klickt, um ihn anzuzeigen. Wenn <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> keine Nachfolgeelemente besitzt, die den Fokus erhalten können, tritt dieses Problem nicht auf. Ein Beispiel für eine entsprechende Situation liegt vor, wenn <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> der Stamm von DataTemplate ist. Wenn dieses Problem erreicht wird, tritt „InvalidCastException“ innerhalb des WPF-Frameworks auf.

#### <a name="suggestion"></a>Vorschlag

Hierfür wird ein Hotfix zur Verfügung gestellt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|
