---
ms.openlocfilehash: 3e8601ba76dfb05e3d70b3af7440bd7e228768d0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621173"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="47937-101">Zulassen von Unicode in URIs, die UNC-Freigaben ähneln</span><span class="sxs-lookup"><span data-stu-id="47937-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="47937-102">Details</span><span class="sxs-lookup"><span data-stu-id="47937-102">Details</span></span>

<span data-ttu-id="47937-103">In <xref:System.Uri?displayProperty=fullName> führt das Erstellen eines Datei-URI, der sowohl einen UNC-Freigabenamen als auch Unicode-Zeichen enthält, nicht mehr zu einem URI mit ungültigem internen Status.</span><span class="sxs-lookup"><span data-stu-id="47937-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="47937-104">Das Verhalten ändert sich erst, wenn alle folgenden Punkte erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="47937-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="47937-105">Der URI hat das Schema <code>file:</code>, auf das vier oder mehr Schrägstriche folgen.</span><span class="sxs-lookup"><span data-stu-id="47937-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="47937-106">Der Hostname beginnt mit einem Unterstrich oder anderem nicht reservierten Symbol.</span><span class="sxs-lookup"><span data-stu-id="47937-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="47937-107">Der URI enthält Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="47937-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="47937-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="47937-108">Suggestion</span></span>

<span data-ttu-id="47937-109">Anwendungen, die mit URIs arbeiten, die durchgängig Unicode enthalten, hätten dieses Verhalten möglicherweise nutzen können, um Verweise auf UNC-Freigaben zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="47937-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="47937-110">Diese Anwendungen sollten stattdessen <xref:System.Uri.IsUnc> verwenden.</span><span class="sxs-lookup"><span data-stu-id="47937-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="47937-111">name</span><span class="sxs-lookup"><span data-stu-id="47937-111">Name</span></span>    | <span data-ttu-id="47937-112">Wert</span><span class="sxs-lookup"><span data-stu-id="47937-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47937-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="47937-113">Scope</span></span>   |<span data-ttu-id="47937-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47937-114">Edge</span></span>|
|<span data-ttu-id="47937-115">Version</span><span class="sxs-lookup"><span data-stu-id="47937-115">Version</span></span>|<span data-ttu-id="47937-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="47937-116">4.7.2</span></span>|
|<span data-ttu-id="47937-117">Typ</span><span class="sxs-lookup"><span data-stu-id="47937-117">Type</span></span>|<span data-ttu-id="47937-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="47937-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47937-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="47937-119">Affected APIs</span></span>

-<xref:System.Uri?displayProperty=nameWithType></li></ul>|
