---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235709"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="d69e2-101">HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="d69e2-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d69e2-102">Details</span><span class="sxs-lookup"><span data-stu-id="d69e2-102">Details</span></span>|<span data-ttu-id="d69e2-103">Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> mit einem Escapezeichen (&amp;) versehen.</span><span class="sxs-lookup"><span data-stu-id="d69e2-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="d69e2-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d69e2-104">Suggestion</span></span>|<span data-ttu-id="d69e2-105">Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d69e2-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="d69e2-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="d69e2-106">Scope</span></span>|<span data-ttu-id="d69e2-107">Gering</span><span class="sxs-lookup"><span data-stu-id="d69e2-107">Minor</span></span>|
|<span data-ttu-id="d69e2-108">Version</span><span class="sxs-lookup"><span data-stu-id="d69e2-108">Version</span></span>|<span data-ttu-id="d69e2-109">4.5</span><span class="sxs-lookup"><span data-stu-id="d69e2-109">4.5</span></span>|
|<span data-ttu-id="d69e2-110">Typ</span><span class="sxs-lookup"><span data-stu-id="d69e2-110">Type</span></span>|<span data-ttu-id="d69e2-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d69e2-111">Runtime</span></span>|
|<span data-ttu-id="d69e2-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d69e2-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
