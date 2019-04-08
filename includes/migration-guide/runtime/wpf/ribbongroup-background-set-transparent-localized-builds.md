---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760635"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="7a03b-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="7a03b-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7a03b-102">Details</span><span class="sxs-lookup"><span data-stu-id="7a03b-102">Details</span></span>|<span data-ttu-id="7a03b-103">Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="7a03b-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="7a03b-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="7a03b-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="7a03b-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7a03b-105">Suggestion</span></span>|<span data-ttu-id="7a03b-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="7a03b-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="7a03b-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="7a03b-107">Scope</span></span>|<span data-ttu-id="7a03b-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7a03b-108">Edge</span></span>|
|<span data-ttu-id="7a03b-109">Version</span><span class="sxs-lookup"><span data-stu-id="7a03b-109">Version</span></span>|<span data-ttu-id="7a03b-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7a03b-110">4.6.2</span></span>|
|<span data-ttu-id="7a03b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="7a03b-111">Type</span></span>|<span data-ttu-id="7a03b-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7a03b-112">Runtime</span></span>|

