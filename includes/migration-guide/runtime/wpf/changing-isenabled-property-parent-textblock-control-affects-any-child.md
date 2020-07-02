---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621258"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
