---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606686"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="9974c-101">HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="9974c-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="9974c-102">Details</span><span class="sxs-lookup"><span data-stu-id="9974c-102">Details</span></span>

<span data-ttu-id="9974c-103">Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> mit einem Escapezeichen (&amp;) versehen.</span><span class="sxs-lookup"><span data-stu-id="9974c-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9974c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9974c-104">Suggestion</span></span>

<span data-ttu-id="9974c-105">Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9974c-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="9974c-106">name</span><span class="sxs-lookup"><span data-stu-id="9974c-106">Name</span></span>    | <span data-ttu-id="9974c-107">Wert</span><span class="sxs-lookup"><span data-stu-id="9974c-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9974c-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="9974c-108">Scope</span></span>   |<span data-ttu-id="9974c-109">Gering</span><span class="sxs-lookup"><span data-stu-id="9974c-109">Minor</span></span>|
|<span data-ttu-id="9974c-110">Version</span><span class="sxs-lookup"><span data-stu-id="9974c-110">Version</span></span>|<span data-ttu-id="9974c-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9974c-111">4.5</span></span>|
|<span data-ttu-id="9974c-112">Typ</span><span class="sxs-lookup"><span data-stu-id="9974c-112">Type</span></span>|<span data-ttu-id="9974c-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9974c-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9974c-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9974c-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
