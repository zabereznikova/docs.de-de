---
ms.openlocfilehash: 12fb72d5ee9fc0d6c57899589cb2b0da7db41f4a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497389"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="44ae4-101">HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="44ae4-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="44ae4-102">Details</span><span class="sxs-lookup"><span data-stu-id="44ae4-102">Details</span></span>

<span data-ttu-id="44ae4-103">Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> mit einem Escapezeichen (&amp;) versehen.</span><span class="sxs-lookup"><span data-stu-id="44ae4-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="44ae4-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="44ae4-104">Suggestion</span></span>

<span data-ttu-id="44ae4-105">Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="44ae4-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="44ae4-106">name</span><span class="sxs-lookup"><span data-stu-id="44ae4-106">Name</span></span>    | <span data-ttu-id="44ae4-107">Wert</span><span class="sxs-lookup"><span data-stu-id="44ae4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="44ae4-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="44ae4-108">Scope</span></span>   |<span data-ttu-id="44ae4-109">Gering</span><span class="sxs-lookup"><span data-stu-id="44ae4-109">Minor</span></span>|
|<span data-ttu-id="44ae4-110">Version</span><span class="sxs-lookup"><span data-stu-id="44ae4-110">Version</span></span>|<span data-ttu-id="44ae4-111">4.5</span><span class="sxs-lookup"><span data-stu-id="44ae4-111">4.5</span></span>|
|<span data-ttu-id="44ae4-112">Typ</span><span class="sxs-lookup"><span data-stu-id="44ae4-112">Type</span></span>|<span data-ttu-id="44ae4-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="44ae4-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="44ae4-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="44ae4-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
