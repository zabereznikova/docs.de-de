---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496202"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="02b09-101">MinFreeMemoryPercentageToActiveService wird jetzt eingehalten</span><span class="sxs-lookup"><span data-stu-id="02b09-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="02b09-102">Details</span><span class="sxs-lookup"><span data-stu-id="02b09-102">Details</span></span>

<span data-ttu-id="02b09-103">Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="02b09-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="02b09-104">Sie dient dazu, <xref:System.OutOfMemoryException?displayProperty=fullName>-Ausnahmen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="02b09-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="02b09-105">In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="02b09-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="02b09-106">In .NET Framework 4.5.1 wird die Einstellung beobachtet.</span><span class="sxs-lookup"><span data-stu-id="02b09-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="02b09-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="02b09-107">Suggestion</span></span>

<span data-ttu-id="02b09-108">Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="02b09-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="02b09-109">Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="02b09-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="02b09-110">name</span><span class="sxs-lookup"><span data-stu-id="02b09-110">Name</span></span>    | <span data-ttu-id="02b09-111">Wert</span><span class="sxs-lookup"><span data-stu-id="02b09-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02b09-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="02b09-112">Scope</span></span>   |<span data-ttu-id="02b09-113">Gering</span><span class="sxs-lookup"><span data-stu-id="02b09-113">Minor</span></span>|
|<span data-ttu-id="02b09-114">Version</span><span class="sxs-lookup"><span data-stu-id="02b09-114">Version</span></span>|<span data-ttu-id="02b09-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="02b09-115">4.5.1</span></span>|
|<span data-ttu-id="02b09-116">Typ</span><span class="sxs-lookup"><span data-stu-id="02b09-116">Type</span></span>|<span data-ttu-id="02b09-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="02b09-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="02b09-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="02b09-118">Affected APIs</span></span>

<span data-ttu-id="02b09-119">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="02b09-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
