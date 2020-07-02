---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620142"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="f3f10-101">HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="f3f10-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="f3f10-102">Details</span><span class="sxs-lookup"><span data-stu-id="f3f10-102">Details</span></span>

<span data-ttu-id="f3f10-103">Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> mit einem Escapezeichen (&amp;) versehen.</span><span class="sxs-lookup"><span data-stu-id="f3f10-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f3f10-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f3f10-104">Suggestion</span></span>

<span data-ttu-id="f3f10-105">Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3f10-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="f3f10-106">name</span><span class="sxs-lookup"><span data-stu-id="f3f10-106">Name</span></span>    | <span data-ttu-id="f3f10-107">Wert</span><span class="sxs-lookup"><span data-stu-id="f3f10-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3f10-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="f3f10-108">Scope</span></span>   |<span data-ttu-id="f3f10-109">Gering</span><span class="sxs-lookup"><span data-stu-id="f3f10-109">Minor</span></span>|
|<span data-ttu-id="f3f10-110">Version</span><span class="sxs-lookup"><span data-stu-id="f3f10-110">Version</span></span>|<span data-ttu-id="f3f10-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f3f10-111">4.5</span></span>|
|<span data-ttu-id="f3f10-112">Typ</span><span class="sxs-lookup"><span data-stu-id="f3f10-112">Type</span></span>|<span data-ttu-id="f3f10-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f3f10-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3f10-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f3f10-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
