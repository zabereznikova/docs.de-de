---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496993"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="09b23-101">Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="09b23-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="09b23-102">Details</span><span class="sxs-lookup"><span data-stu-id="09b23-102">Details</span></span>

<span data-ttu-id="09b23-103">In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="09b23-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="09b23-104">Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09b23-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="09b23-105">Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.</span><span class="sxs-lookup"><span data-stu-id="09b23-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="09b23-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="09b23-106">Suggestion</span></span>

<span data-ttu-id="09b23-107">Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.</span><span class="sxs-lookup"><span data-stu-id="09b23-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="09b23-108">Name</span><span class="sxs-lookup"><span data-stu-id="09b23-108">Name</span></span>    | <span data-ttu-id="09b23-109">Wert</span><span class="sxs-lookup"><span data-stu-id="09b23-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="09b23-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="09b23-110">Scope</span></span>   |<span data-ttu-id="09b23-111">Gering</span><span class="sxs-lookup"><span data-stu-id="09b23-111">Minor</span></span>|
|<span data-ttu-id="09b23-112">Version</span><span class="sxs-lookup"><span data-stu-id="09b23-112">Version</span></span>|<span data-ttu-id="09b23-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="09b23-113">4.6.2</span></span>|
|<span data-ttu-id="09b23-114">Typ</span><span class="sxs-lookup"><span data-stu-id="09b23-114">Type</span></span>|<span data-ttu-id="09b23-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="09b23-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="09b23-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="09b23-116">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
