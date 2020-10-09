---
ms.openlocfilehash: d61a3b3dd855d783d7bff7cb74e5b84969e60860
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608046"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="1fa56-101">Falsche Behandlung von mehrteiligen Elementen in ASP.NET kann zu Datenverlusten bei Formularen führen.</span><span class="sxs-lookup"><span data-stu-id="1fa56-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="1fa56-102">Details</span><span class="sxs-lookup"><span data-stu-id="1fa56-102">Details</span></span>

<span data-ttu-id="1fa56-103">In Anwendungen für .NET Framework 4.7.2 und früher werden mehrteilige Grenzwerte von ASP.NET möglicherweise falsch analysiert, was dazu führt, dass Formulardaten bei der Ausführung einer Anforderung nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1fa56-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.NET might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="1fa56-104">Anwendungen, die .NET Framework 4.8 oder höhere Versionen gezielt nutzen, analysieren mehrteilige Daten ordnungsgemäß, sodass Formularwerte bei der Ausführung von Anforderungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1fa56-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1fa56-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1fa56-105">Suggestion</span></span>

<span data-ttu-id="1fa56-106">Ab Anwendungen, die unter .NET Framework 4.8 ausgeführt werden, ändert sich das Standardverhalten bei gezielter Nutzung von .NET Framework 4.8 oder höher durch Verwenden des <code>targetFrameworkVersion</code>-Elements, und Trennzeichen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="1fa56-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="1fa56-107">Wenn frühere Framework-Versionen gezielt genutzt oder <code>targetFrameworkVersion</code> nicht verwendet wird, werden weiterhin für einige Werte nachstehende Trennzeichen zurückgegeben. Dieses Verhalten kann mit einer <code>appSetting</code> ebenfalls explizit festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="1fa56-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1fa56-108">name</span><span class="sxs-lookup"><span data-stu-id="1fa56-108">Name</span></span>    | <span data-ttu-id="1fa56-109">Wert</span><span class="sxs-lookup"><span data-stu-id="1fa56-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1fa56-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="1fa56-110">Scope</span></span>   |<span data-ttu-id="1fa56-111">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1fa56-111">Unknown</span></span>|
|<span data-ttu-id="1fa56-112">Version</span><span class="sxs-lookup"><span data-stu-id="1fa56-112">Version</span></span>|<span data-ttu-id="1fa56-113">4.8</span><span class="sxs-lookup"><span data-stu-id="1fa56-113">4.8</span></span>|
|<span data-ttu-id="1fa56-114">Typ</span><span class="sxs-lookup"><span data-stu-id="1fa56-114">Type</span></span>|<span data-ttu-id="1fa56-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1fa56-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1fa56-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1fa56-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
