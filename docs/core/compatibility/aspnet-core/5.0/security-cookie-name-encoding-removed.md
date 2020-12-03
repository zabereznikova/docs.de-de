---
title: 'Breaking Change: Sicherheit: Die Codierung für Cookienamen wurde entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Sicherheit: Die Codierung für Cookienamen wurde entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759552"
---
# <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="a406e-103">Sicherheit: Die Codierung für Cookienamen wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="a406e-103">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="a406e-104">Nach dem neuen [Standard für HTTP-Cookies](https://tools.ietf.org/html/rfc6265#section-4.1.1) sind nur bestimmte Zeichen in Cookienamen und -werten zulässig.</span><span class="sxs-lookup"><span data-stu-id="a406e-104">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="a406e-105">Damit nicht zulässige Zeichen unterstützt werden können, tut ASP.NET Core Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a406e-105">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="a406e-106">Wenn ein Antwortcookie erstellt wird, werden die Zeichen codiert.</span><span class="sxs-lookup"><span data-stu-id="a406e-106">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="a406e-107">Wenn ein Anforderungscookie gelesen wird, werden die Zeichen decodiert.</span><span class="sxs-lookup"><span data-stu-id="a406e-107">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="a406e-108">Als Reaktion auf ein Sicherheitsproblem wurde dieses Codierungsverhalten in ASP.NET Core 5.0 geändert.</span><span class="sxs-lookup"><span data-stu-id="a406e-108">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="a406e-109">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="a406e-109">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a406e-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a406e-110">Version introduced</span></span>

<span data-ttu-id="a406e-111">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a406e-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a406e-112">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="a406e-112">Old behavior</span></span>

<span data-ttu-id="a406e-113">Antwortcookienamen wurden codiert.</span><span class="sxs-lookup"><span data-stu-id="a406e-113">Response cookie names are encoded.</span></span> <span data-ttu-id="a406e-114">Anforderungscookienamen wurden decodiert.</span><span class="sxs-lookup"><span data-stu-id="a406e-114">Request cookie names are decoded.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="a406e-115">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="a406e-115">New behavior</span></span>

<span data-ttu-id="a406e-116">Das Codieren und Decodieren von Cookienamen wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="a406e-116">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="a406e-117">Bei bisher [unterstützten Versionen](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) von ASP.NET Core plant das Team, das Decodierungsproblem direkt zu lösen.</span><span class="sxs-lookup"><span data-stu-id="a406e-117">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="a406e-118">Außerdem wird beim Aufrufen von <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> mit einem ungültigen Cookiename eine Ausnahme des Typs <xref:System.ArgumentException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a406e-118">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="a406e-119">Das Codieren und Decodieren von Cookiewerten bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="a406e-119">Encoding and decoding of cookie values remains unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a406e-120">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a406e-120">Reason for change</span></span>

<span data-ttu-id="a406e-121">In [mehreren Webframeworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52) wurde ein Problem entdeckt.</span><span class="sxs-lookup"><span data-stu-id="a406e-121">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="a406e-122">Das Codieren und Decodieren könnte es einem Angreifer ermöglichen, ein Sicherheitsfeature namens [Cookiepräfixe](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) zu umgehen, indem reservierte Präfixe wie `__Host-` mit codierten Werten wie `__%48ost-` per Spoofing manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="a406e-122">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="a406e-123">Für einen solchen Angriff ist ein sekundärer Exploit erforderlich, um die durch Spoofing manipulierten Cookies in die Website zu injizieren, z. B. über ein XSS-Sicherheitsrisiko (Cross-Site-Scripting).</span><span class="sxs-lookup"><span data-stu-id="a406e-123">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="a406e-124">Diese Präfixe werden in ASP.NET Core oder `Microsoft.Owin`-Bibliotheken oder -Vorlagen nicht standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="a406e-124">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a406e-125">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a406e-125">Recommended action</span></span>

<span data-ttu-id="a406e-126">Wenn Sie Projekte zu ASP.NET Core 5.0 oder höher verschieben, sollten Sie dafür sorgen, dass die entsprechen Cookienamen den [Tokenspezifikationsanforderungen](https://tools.ietf.org/html/rfc2616#section-2.2) entsprechen: ASCII-Zeichen außer Steuerzeichen und Trennzeichen (`"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`).</span><span class="sxs-lookup"><span data-stu-id="a406e-126">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="a406e-127">Bei Verwendung von Nicht-ASCII-Zeichen in Cookienamen oder anderen HTTP-Headern kann der Server eine Ausnahme auslösen, oder es wird ein nicht ordnungsgemäßer Roundtrip vom Client durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a406e-127">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a406e-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a406e-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
