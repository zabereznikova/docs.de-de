---
title: 'Breaking Change: Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, bei dem die in RFC 6265 definierten Algorithmen für die Pfadverarbeitung für die Klassen „Cookie“ und „CookieContainer“ implementiert wurden.
ms.date: 08/18/2020
ms.openlocfilehash: 4aea06f434c4bbbef7d94b4b39ff647dd954745e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759397"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="253ef-103">Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform</span><span class="sxs-lookup"><span data-stu-id="253ef-103">Cookie path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="253ef-104">In [RFC 6265](https://tools.ietf.org/html/rfc6265) definierte Pfadverarbeitungsalgorithmen wurden für die Klassen <xref:System.Net.Cookie> und <xref:System.Net.CookieContainer> implementiert.</span><span class="sxs-lookup"><span data-stu-id="253ef-104">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="253ef-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="253ef-105">Version introduced</span></span>

<span data-ttu-id="253ef-106">5.0</span><span class="sxs-lookup"><span data-stu-id="253ef-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="253ef-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="253ef-107">Change description</span></span>

- <span data-ttu-id="253ef-108">Die Eigenschaft <xref:System.Net.Cookie.Path> ist kein erforderliches Präfix für den Anforderungspfad mehr.</span><span class="sxs-lookup"><span data-stu-id="253ef-108">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="253ef-109">Die Berechnung des Standardwerts von <xref:System.Net.Cookie.Path> und der Pfadabgleichalgorithmus wurden wie gemäß [Abschnitt 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) des RFC 6265 implementiert.</span><span class="sxs-lookup"><span data-stu-id="253ef-109">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="253ef-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="253ef-110">Recommended action</span></span>

<span data-ttu-id="253ef-111">In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="253ef-111">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="253ef-112">Wenn Ihr Code jedoch von der <xref:System.Net.Cookie.Path>-Validierung abhängig wäre, müssten Sie die erforderliche Validierung in Ihren Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="253ef-112">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="253ef-113">Wenn Ihr Code von der Standardwertberechnung für <xref:System.Net.Cookie.Path> abhängig wäre, sollten Sie den Wert <xref:System.Net.Cookie.Path> manuell eingeben, anstatt den Standardwert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="253ef-113">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="253ef-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="253ef-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
