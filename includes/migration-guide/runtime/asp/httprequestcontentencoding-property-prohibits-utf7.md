---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496601"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="8ab94-101">HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7</span><span class="sxs-lookup"><span data-stu-id="8ab94-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="8ab94-102">Details</span><span class="sxs-lookup"><span data-stu-id="8ab94-102">Details</span></span>

<span data-ttu-id="8ab94-103">Ab .NET Framework 4.5 ist die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName>-Texten nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8ab94-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="8ab94-104">Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="8ab94-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ab94-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8ab94-105">Suggestion</span></span>

<span data-ttu-id="8ab94-106">Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName> nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ab94-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="8ab94-107">Alternativ kann das Legacyverhalten mithilfe des <code>aspnet:AllowUtf7RequestContentEncoding</code>-Attributs des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)-Elements wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ab94-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="8ab94-108">name</span><span class="sxs-lookup"><span data-stu-id="8ab94-108">Name</span></span>    | <span data-ttu-id="8ab94-109">Wert</span><span class="sxs-lookup"><span data-stu-id="8ab94-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ab94-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="8ab94-110">Scope</span></span>   |<span data-ttu-id="8ab94-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8ab94-111">Edge</span></span>|
|<span data-ttu-id="8ab94-112">Version</span><span class="sxs-lookup"><span data-stu-id="8ab94-112">Version</span></span>|<span data-ttu-id="8ab94-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8ab94-113">4.5</span></span>|
|<span data-ttu-id="8ab94-114">Typ</span><span class="sxs-lookup"><span data-stu-id="8ab94-114">Type</span></span>|<span data-ttu-id="8ab94-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8ab94-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8ab94-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8ab94-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
