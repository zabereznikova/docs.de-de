---
ms.openlocfilehash: dfc1a0d05142861ff1c1b7391126d86e09fa71c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804084"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="79eb8-101">WebUtility.HtmlDecode decodiert keine ungültigen Eingabesequenzen mehr</span><span class="sxs-lookup"><span data-stu-id="79eb8-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

|   |   |
|---|---|
|<span data-ttu-id="79eb8-102">Details</span><span class="sxs-lookup"><span data-stu-id="79eb8-102">Details</span></span>|<span data-ttu-id="79eb8-103">Decodierungsmethoden decodieren nicht mehr standardmäßig ungültige Eingabesequenzen in ungültige UTF-16-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="79eb8-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="79eb8-104">Stattdessen geben sie die ursprüngliche Eingabe zurück.</span><span class="sxs-lookup"><span data-stu-id="79eb8-104">Instead, they return the original input.</span></span>|
|<span data-ttu-id="79eb8-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="79eb8-105">Suggestion</span></span>|<span data-ttu-id="79eb8-106">Die Änderung der Decoderausgabe sollte nur von Bedeutung sein, wenn Sie Binärdaten statt der UTF-16-Daten in Zeichenfolgen speichern.</span><span class="sxs-lookup"><span data-stu-id="79eb8-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="79eb8-107">Um dieses Verhalten explizit zu steuern, legen Sie das <code>aspnet:AllowRelaxedUnicodeDecoding</code>-Attribut des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md)-Elements auf <code>true</code> fest, um Legacyverhalten zu aktivieren, oder auf <code>false</code>, um das aktuelle Verhalten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="79eb8-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>|
|<span data-ttu-id="79eb8-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="79eb8-108">Scope</span></span>|<span data-ttu-id="79eb8-109">Gering</span><span class="sxs-lookup"><span data-stu-id="79eb8-109">Minor</span></span>|
|<span data-ttu-id="79eb8-110">Version</span><span class="sxs-lookup"><span data-stu-id="79eb8-110">Version</span></span>|<span data-ttu-id="79eb8-111">4.5</span><span class="sxs-lookup"><span data-stu-id="79eb8-111">4.5</span></span>|
|<span data-ttu-id="79eb8-112">Typ</span><span class="sxs-lookup"><span data-stu-id="79eb8-112">Type</span></span>|<span data-ttu-id="79eb8-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="79eb8-113">Runtime</span></span>|
|<span data-ttu-id="79eb8-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="79eb8-114">Affected APIs</span></span>|<ul><li><xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
