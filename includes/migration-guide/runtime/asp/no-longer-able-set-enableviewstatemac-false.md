---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803194"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="77b9b-101">EnableViewStateMac kann nicht mehr auf FALSE festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="77b9b-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="77b9b-102">Details</span><span class="sxs-lookup"><span data-stu-id="77b9b-102">Details</span></span>|<span data-ttu-id="77b9b-103">In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> oder <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="77b9b-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="77b9b-104">Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen.</span><span class="sxs-lookup"><span data-stu-id="77b9b-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="77b9b-105">Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="77b9b-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="77b9b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="77b9b-106">Suggestion</span></span>|<span data-ttu-id="77b9b-107">Für EnableViewStateMac muss TRUE angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser Anleitung](https://support.microsoft.com/kb/2915218) erläutert, die in Abhängigkeit zu den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).</span><span class="sxs-lookup"><span data-stu-id="77b9b-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="77b9b-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="77b9b-108">Scope</span></span>|<span data-ttu-id="77b9b-109">Major</span><span class="sxs-lookup"><span data-stu-id="77b9b-109">Major</span></span>|
|<span data-ttu-id="77b9b-110">Version</span><span class="sxs-lookup"><span data-stu-id="77b9b-110">Version</span></span>|<span data-ttu-id="77b9b-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="77b9b-111">4.5.2</span></span>|
|<span data-ttu-id="77b9b-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="77b9b-112">Type</span></span>|<span data-ttu-id="77b9b-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="77b9b-113">Runtime</span></span>|
