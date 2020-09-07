---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497675"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="58171-101">WebUtility.HtmlDecode decodiert keine ungültigen Eingabesequenzen mehr</span><span class="sxs-lookup"><span data-stu-id="58171-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="58171-102">Details</span><span class="sxs-lookup"><span data-stu-id="58171-102">Details</span></span>

<span data-ttu-id="58171-103">Decodierungsmethoden decodieren nicht mehr standardmäßig ungültige Eingabesequenzen in ungültige UTF-16-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="58171-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="58171-104">Stattdessen geben sie die ursprüngliche Eingabe zurück.</span><span class="sxs-lookup"><span data-stu-id="58171-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58171-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="58171-105">Suggestion</span></span>

<span data-ttu-id="58171-106">Die Änderung der Decoderausgabe sollte nur von Bedeutung sein, wenn Sie Binärdaten statt der UTF-16-Daten in Zeichenfolgen speichern.</span><span class="sxs-lookup"><span data-stu-id="58171-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="58171-107">Um dieses Verhalten explizit zu steuern, legen Sie das <code>aspnet:AllowRelaxedUnicodeDecoding</code>-Attribut des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md)-Elements auf <code>true</code> fest, um Legacyverhalten zu aktivieren, oder auf <code>false</code>, um das aktuelle Verhalten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58171-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="58171-108">name</span><span class="sxs-lookup"><span data-stu-id="58171-108">Name</span></span>    | <span data-ttu-id="58171-109">Wert</span><span class="sxs-lookup"><span data-stu-id="58171-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58171-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="58171-110">Scope</span></span>   |<span data-ttu-id="58171-111">Gering</span><span class="sxs-lookup"><span data-stu-id="58171-111">Minor</span></span>|
|<span data-ttu-id="58171-112">Version</span><span class="sxs-lookup"><span data-stu-id="58171-112">Version</span></span>|<span data-ttu-id="58171-113">4.5</span><span class="sxs-lookup"><span data-stu-id="58171-113">4.5</span></span>|
|<span data-ttu-id="58171-114">Typ</span><span class="sxs-lookup"><span data-stu-id="58171-114">Type</span></span>|<span data-ttu-id="58171-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="58171-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58171-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="58171-116">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
