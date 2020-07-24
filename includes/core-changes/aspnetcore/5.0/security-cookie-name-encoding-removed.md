---
ms.openlocfilehash: 492d3e61acff31d3d6858a1c27cf353b04a05e36
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401977"
---
### <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="4e618-101">Sicherheit: Die Codierung für Cookienamen wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="4e618-101">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="4e618-102">Nach dem neuen [Standard für HTTP-Cookies](https://tools.ietf.org/html/rfc6265#section-4.1.1) sind nur bestimmte Zeichen in Cookienamen und -werten zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e618-102">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="4e618-103">Damit nicht zulässige Zeichen unterstützt werden können, tut ASP.NET Core Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4e618-103">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="4e618-104">Wenn ein Antwortcookie erstellt wird, werden die Zeichen codiert.</span><span class="sxs-lookup"><span data-stu-id="4e618-104">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="4e618-105">Wenn ein Anforderungscookie gelesen wird, werden die Zeichen decodiert.</span><span class="sxs-lookup"><span data-stu-id="4e618-105">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="4e618-106">Als Reaktion auf ein Sicherheitsproblem wurde dieses Codierungsverhalten in ASP.NET Core 5.0 geändert.</span><span class="sxs-lookup"><span data-stu-id="4e618-106">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="4e618-107">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="4e618-107">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e618-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4e618-108">Version introduced</span></span>

<span data-ttu-id="4e618-109">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="4e618-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4e618-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="4e618-110">Old behavior</span></span>

<span data-ttu-id="4e618-111">Antwortcookienamen wurden codiert.</span><span class="sxs-lookup"><span data-stu-id="4e618-111">Response cookie names are encoded.</span></span> <span data-ttu-id="4e618-112">Anforderungscookienamen wurden decodiert.</span><span class="sxs-lookup"><span data-stu-id="4e618-112">Request cookie names are decoded.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4e618-113">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="4e618-113">New behavior</span></span>

<span data-ttu-id="4e618-114">Das Codieren und Decodieren von Cookienamen wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="4e618-114">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="4e618-115">Bei bisher [unterstützten Versionen](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) von ASP.NET Core plant das Team, das Decodierungsproblem direkt zu lösen.</span><span class="sxs-lookup"><span data-stu-id="4e618-115">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="4e618-116">Außerdem wird beim Aufrufen von <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> mit einem ungültigen Cookiename eine Ausnahme des Typs <xref:System.ArgumentException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4e618-116">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="4e618-117">Das Codieren und Decodieren von Cookiewerten bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="4e618-117">Encoding and decoding of cookie values remains unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4e618-118">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="4e618-118">Reason for change</span></span>

<span data-ttu-id="4e618-119">In [mehreren Webframeworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52) wurde ein Problem entdeckt.</span><span class="sxs-lookup"><span data-stu-id="4e618-119">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="4e618-120">Das Codieren und Decodieren könnte es einem Angreifer ermöglichen, ein Sicherheitsfeature namens [Cookiepräfixe](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) zu umgehen, indem reservierte Präfixe wie `__Host-` mit codierten Werten wie `__%48ost-` per Spoofing manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="4e618-120">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="4e618-121">Für einen solchen Angriff ist ein sekundärer Exploit erforderlich, um die durch Spoofing manipulierten Cookies in die Website zu injizieren, z. B. über ein XSS-Sicherheitsrisiko (Cross-Site-Scripting).</span><span class="sxs-lookup"><span data-stu-id="4e618-121">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="4e618-122">Diese Präfixe werden in ASP.NET Core oder `Microsoft.Owin`-Bibliotheken oder -Vorlagen nicht standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e618-122">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e618-123">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="4e618-123">Recommended action</span></span>

<span data-ttu-id="4e618-124">Wenn Sie Projekte zu ASP.NET Core 5.0 oder höher verschieben, sollten Sie dafür sorgen, dass die entsprechen Cookienamen den [Tokenspezifikationsanforderungen](https://tools.ietf.org/html/rfc2616#section-2.2) entsprechen: ASCII-Zeichen außer Steuerzeichen und Trennzeichen (`"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`).</span><span class="sxs-lookup"><span data-stu-id="4e618-124">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="4e618-125">Bei Verwendung von Nicht-ASCII-Zeichen in Cookienamen oder anderen HTTP-Headern kann der Server eine Ausnahme auslösen, oder es wird ein nicht ordnungsgemäßer Roundtrip vom Client durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e618-125">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

#### <a name="category"></a><span data-ttu-id="4e618-126">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4e618-126">Category</span></span>

<span data-ttu-id="4e618-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4e618-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e618-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4e618-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
