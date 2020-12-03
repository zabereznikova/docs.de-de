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
# <a name="security-cookie-name-encoding-removed"></a>Sicherheit: Die Codierung für Cookienamen wurde entfernt

Nach dem neuen [Standard für HTTP-Cookies](https://tools.ietf.org/html/rfc6265#section-4.1.1) sind nur bestimmte Zeichen in Cookienamen und -werten zulässig. Damit nicht zulässige Zeichen unterstützt werden können, tut ASP.NET Core Folgendes:

* Wenn ein Antwortcookie erstellt wird, werden die Zeichen codiert.
* Wenn ein Anforderungscookie gelesen wird, werden die Zeichen decodiert.

Als Reaktion auf ein Sicherheitsproblem wurde dieses Codierungsverhalten in ASP.NET Core 5.0 geändert.

Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

## <a name="old-behavior"></a>Altes Verhalten

Antwortcookienamen wurden codiert. Anforderungscookienamen wurden decodiert.

## <a name="new-behavior"></a>Neues Verhalten

Das Codieren und Decodieren von Cookienamen wurde entfernt. Bei bisher [unterstützten Versionen](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) von ASP.NET Core plant das Team, das Decodierungsproblem direkt zu lösen. Außerdem wird beim Aufrufen von <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> mit einem ungültigen Cookiename eine Ausnahme des Typs <xref:System.ArgumentException> zurückgegeben. Das Codieren und Decodieren von Cookiewerten bleibt unverändert.

## <a name="reason-for-change"></a>Grund für die Änderung

In [mehreren Webframeworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52) wurde ein Problem entdeckt. Das Codieren und Decodieren könnte es einem Angreifer ermöglichen, ein Sicherheitsfeature namens [Cookiepräfixe](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) zu umgehen, indem reservierte Präfixe wie `__Host-` mit codierten Werten wie `__%48ost-` per Spoofing manipuliert werden. Für einen solchen Angriff ist ein sekundärer Exploit erforderlich, um die durch Spoofing manipulierten Cookies in die Website zu injizieren, z. B. über ein XSS-Sicherheitsrisiko (Cross-Site-Scripting). Diese Präfixe werden in ASP.NET Core oder `Microsoft.Owin`-Bibliotheken oder -Vorlagen nicht standardmäßig verwendet.

## <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie Projekte zu ASP.NET Core 5.0 oder höher verschieben, sollten Sie dafür sorgen, dass die entsprechen Cookienamen den [Tokenspezifikationsanforderungen](https://tools.ietf.org/html/rfc2616#section-2.2) entsprechen: ASCII-Zeichen außer Steuerzeichen und Trennzeichen (`"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`). Bei Verwendung von Nicht-ASCII-Zeichen in Cookienamen oder anderen HTTP-Headern kann der Server eine Ausnahme auslösen, oder es wird ein nicht ordnungsgemäßer Roundtrip vom Client durchgeführt.

## <a name="affected-apis"></a>Betroffene APIs

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
