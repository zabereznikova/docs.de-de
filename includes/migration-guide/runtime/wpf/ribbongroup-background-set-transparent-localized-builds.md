---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802495"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt

|   |   |
|---|---|
|Details|Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte. Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.|
|Vorschlag|Upgrade auf .NET Framework 4.7|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
