---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620166"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="ae92b-101">EnableViewStateMac kann nicht mehr auf FALSE festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="ae92b-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="ae92b-102">Details</span><span class="sxs-lookup"><span data-stu-id="ae92b-102">Details</span></span>

<span data-ttu-id="ae92b-103">In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> oder <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="ae92b-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="ae92b-104">Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen.</span><span class="sxs-lookup"><span data-stu-id="ae92b-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="ae92b-105">Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="ae92b-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae92b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ae92b-106">Suggestion</span></span>

<span data-ttu-id="ae92b-107">Für EnableViewStateMac muss TRUE angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser Anleitung](https://support.microsoft.com/kb/2915218) erläutert, die in Abhängigkeit zu den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).</span><span class="sxs-lookup"><span data-stu-id="ae92b-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="ae92b-108">name</span><span class="sxs-lookup"><span data-stu-id="ae92b-108">Name</span></span>    | <span data-ttu-id="ae92b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="ae92b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae92b-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="ae92b-110">Scope</span></span>   |<span data-ttu-id="ae92b-111">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="ae92b-111">Major</span></span>|
|<span data-ttu-id="ae92b-112">Version</span><span class="sxs-lookup"><span data-stu-id="ae92b-112">Version</span></span>|<span data-ttu-id="ae92b-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ae92b-113">4.5.2</span></span>|
|<span data-ttu-id="ae92b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="ae92b-114">Type</span></span>|<span data-ttu-id="ae92b-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ae92b-115">Runtime</span></span>|
