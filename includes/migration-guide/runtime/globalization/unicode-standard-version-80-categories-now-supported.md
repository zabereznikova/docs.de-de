---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621186"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="96887-101">Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="96887-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="96887-102">Details</span><span class="sxs-lookup"><span data-stu-id="96887-102">Details</span></span>

<span data-ttu-id="96887-103">In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="96887-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="96887-104">Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96887-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="96887-105">Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.</span><span class="sxs-lookup"><span data-stu-id="96887-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96887-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="96887-106">Suggestion</span></span>

<span data-ttu-id="96887-107">Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.</span><span class="sxs-lookup"><span data-stu-id="96887-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="96887-108">Name</span><span class="sxs-lookup"><span data-stu-id="96887-108">Name</span></span>    | <span data-ttu-id="96887-109">Wert</span><span class="sxs-lookup"><span data-stu-id="96887-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96887-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="96887-110">Scope</span></span>   |<span data-ttu-id="96887-111">Gering</span><span class="sxs-lookup"><span data-stu-id="96887-111">Minor</span></span>|
|<span data-ttu-id="96887-112">Version</span><span class="sxs-lookup"><span data-stu-id="96887-112">Version</span></span>|<span data-ttu-id="96887-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="96887-113">4.6.2</span></span>|
|<span data-ttu-id="96887-114">Typ</span><span class="sxs-lookup"><span data-stu-id="96887-114">Type</span></span>|<span data-ttu-id="96887-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="96887-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="96887-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="96887-116">Affected APIs</span></span>

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
