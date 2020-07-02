---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620130"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="6c92a-101">HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7</span><span class="sxs-lookup"><span data-stu-id="6c92a-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="6c92a-102">Details</span><span class="sxs-lookup"><span data-stu-id="6c92a-102">Details</span></span>

<span data-ttu-id="6c92a-103">Ab .NET Framework 4.5 ist die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName>-Texten nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="6c92a-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="6c92a-104">Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="6c92a-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6c92a-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6c92a-105">Suggestion</span></span>

<span data-ttu-id="6c92a-106">Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName> nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c92a-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="6c92a-107">Alternativ kann das Legacyverhalten mithilfe des <code>aspnet:AllowUtf7RequestContentEncoding</code>-Attributs des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)-Elements wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c92a-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="6c92a-108">name</span><span class="sxs-lookup"><span data-stu-id="6c92a-108">Name</span></span>    | <span data-ttu-id="6c92a-109">Wert</span><span class="sxs-lookup"><span data-stu-id="6c92a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6c92a-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="6c92a-110">Scope</span></span>   |<span data-ttu-id="6c92a-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6c92a-111">Edge</span></span>|
|<span data-ttu-id="6c92a-112">Version</span><span class="sxs-lookup"><span data-stu-id="6c92a-112">Version</span></span>|<span data-ttu-id="6c92a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6c92a-113">4.5</span></span>|
|<span data-ttu-id="6c92a-114">Typ</span><span class="sxs-lookup"><span data-stu-id="6c92a-114">Type</span></span>|<span data-ttu-id="6c92a-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6c92a-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c92a-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6c92a-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
