---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465511"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="8c6ed-101">Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform</span><span class="sxs-lookup"><span data-stu-id="8c6ed-101">Cookie Path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="8c6ed-102">In [RFC 6265](https://tools.ietf.org/html/rfc6265) definierte Pfadverarbeitungsalgorithmen wurden für die Klassen <xref:System.Net.Cookie> und <xref:System.Net.CookieContainer> implementiert.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-102">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8c6ed-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8c6ed-103">Version introduced</span></span>

<span data-ttu-id="8c6ed-104">5.0</span><span class="sxs-lookup"><span data-stu-id="8c6ed-104">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="8c6ed-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8c6ed-105">Change description</span></span>

- <span data-ttu-id="8c6ed-106">Die Eigenschaft <xref:System.Net.Cookie.Path> ist kein erforderliches Präfix für den Anforderungspfad mehr.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-106">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="8c6ed-107">Die Berechnung des Standardwerts von <xref:System.Net.Cookie.Path> und der Pfadabgleichalgorithmus wurden wie gemäß [Abschnitt 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) des RFC 6265 implementiert.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-107">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8c6ed-108">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8c6ed-108">Recommended action</span></span>

<span data-ttu-id="8c6ed-109">In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-109">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="8c6ed-110">Wenn Ihr Code jedoch von der <xref:System.Net.Cookie.Path>-Validierung abhängig wäre, müssten Sie die erforderliche Validierung in Ihren Code implementieren.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-110">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="8c6ed-111">Wenn Ihr Code von der Standardwertberechnung für <xref:System.Net.Cookie.Path> abhängig wäre, sollten Sie den Wert <xref:System.Net.Cookie.Path> manuell eingeben, anstatt den Standardwert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c6ed-111">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

#### <a name="category"></a><span data-ttu-id="8c6ed-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8c6ed-112">Category</span></span>

<span data-ttu-id="8c6ed-113">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="8c6ed-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8c6ed-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8c6ed-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
