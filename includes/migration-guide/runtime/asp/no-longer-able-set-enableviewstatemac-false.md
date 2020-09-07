---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497534"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="892df-101">EnableViewStateMac kann nicht mehr auf FALSE festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="892df-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="892df-102">Details</span><span class="sxs-lookup"><span data-stu-id="892df-102">Details</span></span>

<span data-ttu-id="892df-103">In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> oder <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="892df-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="892df-104">Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen.</span><span class="sxs-lookup"><span data-stu-id="892df-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="892df-105">Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="892df-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="892df-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="892df-106">Suggestion</span></span>

<span data-ttu-id="892df-107">Für EnableViewStateMac muss TRUE angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser Anleitung](https://support.microsoft.com/kb/2915218) erläutert, die in Abhängigkeit zu den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).</span><span class="sxs-lookup"><span data-stu-id="892df-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="892df-108">name</span><span class="sxs-lookup"><span data-stu-id="892df-108">Name</span></span>    | <span data-ttu-id="892df-109">Wert</span><span class="sxs-lookup"><span data-stu-id="892df-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="892df-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="892df-110">Scope</span></span>   |<span data-ttu-id="892df-111">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="892df-111">Major</span></span>|
|<span data-ttu-id="892df-112">Version</span><span class="sxs-lookup"><span data-stu-id="892df-112">Version</span></span>|<span data-ttu-id="892df-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="892df-113">4.5.2</span></span>|
|<span data-ttu-id="892df-114">Typ</span><span class="sxs-lookup"><span data-stu-id="892df-114">Type</span></span>|<span data-ttu-id="892df-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="892df-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="892df-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="892df-116">Affected APIs</span></span>

<span data-ttu-id="892df-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="892df-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
