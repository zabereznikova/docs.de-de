---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497371"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Das Ändern der IsEnabled-Eigenschaft des übergeordneten Elements eines TextBlock-Steuerelements wirkt sich auf alle untergeordneten Steuerelemente aus

#### <a name="details"></a>Details

Ab .NET Framework 4.6.2 wirkt sich das Ändern der <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>-Eigenschaft eines übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements auf alle untergeordneten Steuerelemente (z.B. Links und Schaltflächen) des <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements aus. In .NET Framework 4.6.1 und früher zeigten Steuerelemente innerhalb von <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> nicht immer den Status der <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>-Eigenschaft des übergeordneten <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Elements an.

#### <a name="suggestion"></a>Vorschlag

Keine. Diese Änderung entspricht dem erwarteten Verhalten für Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
