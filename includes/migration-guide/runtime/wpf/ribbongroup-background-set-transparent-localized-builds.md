---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497542"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt

#### <a name="details"></a>Details

Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte. Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.

#### <a name="suggestion"></a>Vorschlag

Upgrade auf .NET Framework 4.7

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
