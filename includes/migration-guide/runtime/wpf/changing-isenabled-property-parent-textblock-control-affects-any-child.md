---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857566"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Das Ändern der IsEnabled-Eigenschaft des übergeordneten Elements eines TextBlock-Steuerelements wirkt sich auf alle untergeordneten Steuerelemente aus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 wirkt sich das Ändern der <xref:System.Windows.UIElement.IsEnabled?displayProperty=name>-Eigenschaft eines übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements auf alle untergeordneten Steuerelemente (z.B. Links und Schaltflächen) des <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements aus. In .NET Framework 4.6.1 und früher zeigten Steuerelemente innerhalb von <xref:System.Windows.Controls.TextBlock?displayProperty=name> nicht immer den Status der <xref:System.Windows.UIElement.IsEnabled?displayProperty=name>-Eigenschaft des übergeordneten <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Elements an.|
|Vorschlag|Keine. Diese Änderung entspricht dem erwarteten Verhalten für Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements.|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
