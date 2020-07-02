---
ms.openlocfilehash: 08a9292c5a41e7b9b7c1bcc18ec96460de19863f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621185"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="c906f-101">Unterstützen einer besonderen relativen URI-Notation, wenn Unicode vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="c906f-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="c906f-102">Details</span><span class="sxs-lookup"><span data-stu-id="c906f-102">Details</span></span>

<span data-ttu-id="c906f-103"><xref:System.Uri> löst keine <xref:System.NullReferenceException> mehr aus, wenn <xref:System.Uri.TryCreate%2A> für bestimmte relative URIs, die Unicode enthalten, aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c906f-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="c906f-104">Am einfachsten können Sie die <xref:System.NullReferenceException> mit dem folgenden Code selbst nachvollziehen. Beide Anweisungen sind gleichwertig:</span><span class="sxs-lookup"><span data-stu-id="c906f-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="c906f-105">Zum Reproduzieren der <xref:System.NullReferenceException> müssen die folgenden Punkte zutreffen:</span><span class="sxs-lookup"><span data-stu-id="c906f-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="c906f-106">Die URI muss als relativ angegeben werden, indem ihm „http:“ vorangestellt wird, anstatt dass „//“ auf ihn folgt.</span><span class="sxs-lookup"><span data-stu-id="c906f-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="c906f-107">Die URI muss als Prozentwert codiertes Unicode oder nicht reservierte Symbole enthalten.</span><span class="sxs-lookup"><span data-stu-id="c906f-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="c906f-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c906f-108">Suggestion</span></span>

<span data-ttu-id="c906f-109">Benutzer, die zum Unterbinden relativer URIs von diesem Verhalten abhängig sind, sollten stattdessen beim Erstellen eines URI <xref:System.UriKind.Absolute?displayProperty=nameWithType> angeben.</span><span class="sxs-lookup"><span data-stu-id="c906f-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="c906f-110">name</span><span class="sxs-lookup"><span data-stu-id="c906f-110">Name</span></span>    | <span data-ttu-id="c906f-111">Wert</span><span class="sxs-lookup"><span data-stu-id="c906f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c906f-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="c906f-112">Scope</span></span>   |<span data-ttu-id="c906f-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c906f-113">Edge</span></span>|
|<span data-ttu-id="c906f-114">Version</span><span class="sxs-lookup"><span data-stu-id="c906f-114">Version</span></span>|<span data-ttu-id="c906f-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c906f-115">4.7.2</span></span>|
|<span data-ttu-id="c906f-116">Typ</span><span class="sxs-lookup"><span data-stu-id="c906f-116">Type</span></span>|<span data-ttu-id="c906f-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c906f-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c906f-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c906f-118">Affected APIs</span></span>

-<xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
