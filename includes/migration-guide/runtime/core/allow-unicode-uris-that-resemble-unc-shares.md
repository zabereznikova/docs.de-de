---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497437"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="6ee7d-101">Zulassen von Unicode in URIs, die UNC-Freigaben ähneln</span><span class="sxs-lookup"><span data-stu-id="6ee7d-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="6ee7d-102">Details</span><span class="sxs-lookup"><span data-stu-id="6ee7d-102">Details</span></span>

<span data-ttu-id="6ee7d-103">In <xref:System.Uri?displayProperty=fullName> führt das Erstellen eines Datei-URI, der sowohl einen UNC-Freigabenamen als auch Unicode-Zeichen enthält, nicht mehr zu einem URI mit ungültigem internen Status.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="6ee7d-104">Das Verhalten ändert sich erst, wenn alle folgenden Punkte erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="6ee7d-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="6ee7d-105">Der URI hat das Schema <code>file:</code>, auf das vier oder mehr Schrägstriche folgen.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="6ee7d-106">Der Hostname beginnt mit einem Unterstrich oder anderem nicht reservierten Symbol.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="6ee7d-107">Der URI enthält Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="6ee7d-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6ee7d-108">Suggestion</span></span>

<span data-ttu-id="6ee7d-109">Anwendungen, die mit URIs arbeiten, die durchgängig Unicode enthalten, hätten dieses Verhalten möglicherweise nutzen können, um Verweise auf UNC-Freigaben zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="6ee7d-110">Diese Anwendungen sollten stattdessen <xref:System.Uri.IsUnc> verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ee7d-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="6ee7d-111">name</span><span class="sxs-lookup"><span data-stu-id="6ee7d-111">Name</span></span>    | <span data-ttu-id="6ee7d-112">Wert</span><span class="sxs-lookup"><span data-stu-id="6ee7d-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6ee7d-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="6ee7d-113">Scope</span></span>   |<span data-ttu-id="6ee7d-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6ee7d-114">Edge</span></span>|
|<span data-ttu-id="6ee7d-115">Version</span><span class="sxs-lookup"><span data-stu-id="6ee7d-115">Version</span></span>|<span data-ttu-id="6ee7d-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="6ee7d-116">4.7.2</span></span>|
|<span data-ttu-id="6ee7d-117">Typ</span><span class="sxs-lookup"><span data-stu-id="6ee7d-117">Type</span></span>|<span data-ttu-id="6ee7d-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6ee7d-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6ee7d-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6ee7d-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
