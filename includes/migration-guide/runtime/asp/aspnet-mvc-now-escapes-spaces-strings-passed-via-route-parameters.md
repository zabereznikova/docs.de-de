---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496211"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="718ea-101">ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="718ea-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="718ea-102">Details</span><span class="sxs-lookup"><span data-stu-id="718ea-102">Details</span></span>

<span data-ttu-id="718ea-103">Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="718ea-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="718ea-104">Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.</span><span class="sxs-lookup"><span data-stu-id="718ea-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="718ea-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="718ea-105">Suggestion</span></span>

<span data-ttu-id="718ea-106">Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="718ea-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="718ea-107">Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="718ea-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="718ea-108">name</span><span class="sxs-lookup"><span data-stu-id="718ea-108">Name</span></span>    | <span data-ttu-id="718ea-109">Wert</span><span class="sxs-lookup"><span data-stu-id="718ea-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="718ea-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="718ea-110">Scope</span></span>   |<span data-ttu-id="718ea-111">Gering</span><span class="sxs-lookup"><span data-stu-id="718ea-111">Minor</span></span>|
|<span data-ttu-id="718ea-112">Version</span><span class="sxs-lookup"><span data-stu-id="718ea-112">Version</span></span>|<span data-ttu-id="718ea-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="718ea-113">4.5.2</span></span>|
|<span data-ttu-id="718ea-114">Typ</span><span class="sxs-lookup"><span data-stu-id="718ea-114">Type</span></span>|<span data-ttu-id="718ea-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="718ea-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="718ea-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="718ea-116">Affected APIs</span></span>

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
