---
ms.openlocfilehash: 44cb833fc93caaa79000147421e1c013f755b9cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68238028"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>IsSelected-Bindungsfehler für ListBoxItem mit ObservableCollection&lt;T&gt;.Move

|   |   |
|---|---|
|Details|Wenn <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oder <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> für eine Auflistung aufgerufen werden, die über aktivierte Elemente an ein <xref:System.Windows.Controls.ListBox?displayProperty=name>-Element gebunden ist, können bei der (De-)Aktivierung von <xref:System.Windows.Controls.ListBox?displayProperty=name>-Elementen Fehler auftreten.|
|Vorschlag|Wenn Sie anstelle von <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)><xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=name> und <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=name> aufrufen, kann dieser Fehler umgangen werden. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
