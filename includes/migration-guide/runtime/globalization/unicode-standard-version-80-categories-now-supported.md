---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857540"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="c9f59-101">Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="c9f59-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c9f59-102">Details</span><span class="sxs-lookup"><span data-stu-id="c9f59-102">Details</span></span>|<span data-ttu-id="c9f59-103">In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c9f59-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="c9f59-104">Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9f59-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="c9f59-105">Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.</span><span class="sxs-lookup"><span data-stu-id="c9f59-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="c9f59-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c9f59-106">Suggestion</span></span>|<span data-ttu-id="c9f59-107">Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.</span><span class="sxs-lookup"><span data-stu-id="c9f59-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="c9f59-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="c9f59-108">Scope</span></span>|<span data-ttu-id="c9f59-109">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="c9f59-109">Minor</span></span>|
|<span data-ttu-id="c9f59-110">Version</span><span class="sxs-lookup"><span data-stu-id="c9f59-110">Version</span></span>|<span data-ttu-id="c9f59-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c9f59-111">4.6.2</span></span>|
|<span data-ttu-id="c9f59-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9f59-112">Type</span></span>|<span data-ttu-id="c9f59-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c9f59-113">Runtime</span></span>|
|<span data-ttu-id="c9f59-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c9f59-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
