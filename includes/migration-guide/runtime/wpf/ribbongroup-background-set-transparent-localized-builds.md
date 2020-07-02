---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622356"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt

#### <a name="details"></a>Details

Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte. Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.

#### <a name="suggestion"></a>Vorschlag

Upgrade auf .NET Framework 4.7

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit|
