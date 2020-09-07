---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497543"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="c8f04-101">Unterstützen einer besonderen relativen URI-Notation, wenn Unicode vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="c8f04-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="c8f04-102">Details</span><span class="sxs-lookup"><span data-stu-id="c8f04-102">Details</span></span>

<span data-ttu-id="c8f04-103"><xref:System.Uri> löst keine <xref:System.NullReferenceException> mehr aus, wenn <xref:System.Uri.TryCreate%2A> für bestimmte relative URIs, die Unicode enthalten, aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c8f04-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="c8f04-104">Am einfachsten können Sie die <xref:System.NullReferenceException> mit dem folgenden Code selbst nachvollziehen. Beide Anweisungen sind gleichwertig:</span><span class="sxs-lookup"><span data-stu-id="c8f04-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="c8f04-105">Zum Reproduzieren der <xref:System.NullReferenceException> müssen die folgenden Punkte zutreffen:</span><span class="sxs-lookup"><span data-stu-id="c8f04-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="c8f04-106">Die URI muss als relativ angegeben werden, indem ihm „http:“ vorangestellt wird, anstatt dass „//“ auf ihn folgt.</span><span class="sxs-lookup"><span data-stu-id="c8f04-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="c8f04-107">Die URI muss als Prozentwert codiertes Unicode oder nicht reservierte Symbole enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8f04-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="c8f04-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c8f04-108">Suggestion</span></span>

<span data-ttu-id="c8f04-109">Benutzer, die zum Unterbinden relativer URIs von diesem Verhalten abhängig sind, sollten stattdessen beim Erstellen eines URI <xref:System.UriKind.Absolute?displayProperty=nameWithType> angeben.</span><span class="sxs-lookup"><span data-stu-id="c8f04-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="c8f04-110">name</span><span class="sxs-lookup"><span data-stu-id="c8f04-110">Name</span></span>    | <span data-ttu-id="c8f04-111">Wert</span><span class="sxs-lookup"><span data-stu-id="c8f04-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c8f04-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="c8f04-112">Scope</span></span>   |<span data-ttu-id="c8f04-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c8f04-113">Edge</span></span>|
|<span data-ttu-id="c8f04-114">Version</span><span class="sxs-lookup"><span data-stu-id="c8f04-114">Version</span></span>|<span data-ttu-id="c8f04-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c8f04-115">4.7.2</span></span>|
|<span data-ttu-id="c8f04-116">Typ</span><span class="sxs-lookup"><span data-stu-id="c8f04-116">Type</span></span>|<span data-ttu-id="c8f04-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c8f04-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c8f04-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c8f04-118">Affected APIs</span></span>

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
