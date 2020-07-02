---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620448"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>IsSelected-Bindungsfehler für ListBoxItem mit ObservableCollection&lt;T&gt;.Move

#### <a name="details"></a>Details

Wenn <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oder <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> für eine Auflistung aufgerufen werden, die über aktivierte Elemente an ein <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Element gebunden ist, können bei der (De-)Aktivierung von <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Elementen Fehler auftreten.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie anstelle von <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)><xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> und <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> aufrufen, kann dieser Fehler umgangen werden. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
