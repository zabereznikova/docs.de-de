---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617164"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="0f6af-101">WebUtility.HtmlEncode und WebUtility.HtmlDecode führen für die BMP eine ordnungsgemäße Roundtripkonvertierung durch</span><span class="sxs-lookup"><span data-stu-id="0f6af-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="0f6af-102">Details</span><span class="sxs-lookup"><span data-stu-id="0f6af-102">Details</span></span>

<span data-ttu-id="0f6af-103">Bei Anwendungen mit der Zielplattform .NET Framework 4.5 wird für Zeichen, die sich außerhalb der Basic Multilingual Plane (BMP) befinden, eine erfolgreiche Roundtripkonvertierung durchgeführt, wenn sie an die <xref:System.Net.WebUtility.HtmlDecode(System.String)>-Methoden übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0f6af-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0f6af-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0f6af-104">Suggestion</span></span>

<span data-ttu-id="0f6af-105">Diese Änderung sollte keine Auswirkung auf aktuelle Anwendungen haben. Wenn Sie jedoch das ursprüngliche Verhalten wiederherstellen möchten, legen Sie das Attribut `targetFramework` des Elements `<httpRuntime>` auf eine andere Zeichenfolge als „4.5“ fest.</span><span class="sxs-lookup"><span data-stu-id="0f6af-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="0f6af-106">Sie können die `unicodeEncodingConformance`- und `unicodeDecodingConformance`-Attribute des `<webUtility>`-Konfigurationselements auch festlegen, um dieses Verhalten unabhängig von der Zielversion von .NET Framework zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0f6af-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="0f6af-107">name</span><span class="sxs-lookup"><span data-stu-id="0f6af-107">Name</span></span>    | <span data-ttu-id="0f6af-108">Wert</span><span class="sxs-lookup"><span data-stu-id="0f6af-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0f6af-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="0f6af-109">Scope</span></span>   | <span data-ttu-id="0f6af-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f6af-110">Edge</span></span>        |
| <span data-ttu-id="0f6af-111">Version</span><span class="sxs-lookup"><span data-stu-id="0f6af-111">Version</span></span> | <span data-ttu-id="0f6af-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0f6af-112">4.5</span></span>         |
| <span data-ttu-id="0f6af-113">Typ</span><span class="sxs-lookup"><span data-stu-id="0f6af-113">Type</span></span>    | <span data-ttu-id="0f6af-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="0f6af-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="0f6af-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0f6af-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
