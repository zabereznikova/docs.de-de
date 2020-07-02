---
ms.openlocfilehash: c53fe57f3278741a927a2f00b11af6e26dafce66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620153"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="38147-101">ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="38147-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="38147-102">Details</span><span class="sxs-lookup"><span data-stu-id="38147-102">Details</span></span>

<span data-ttu-id="38147-103">Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="38147-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="38147-104">Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.</span><span class="sxs-lookup"><span data-stu-id="38147-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="38147-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="38147-105">Suggestion</span></span>

<span data-ttu-id="38147-106">Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="38147-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="38147-107">Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="38147-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="38147-108">name</span><span class="sxs-lookup"><span data-stu-id="38147-108">Name</span></span>    | <span data-ttu-id="38147-109">Wert</span><span class="sxs-lookup"><span data-stu-id="38147-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="38147-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="38147-110">Scope</span></span>   |<span data-ttu-id="38147-111">Gering</span><span class="sxs-lookup"><span data-stu-id="38147-111">Minor</span></span>|
|<span data-ttu-id="38147-112">Version</span><span class="sxs-lookup"><span data-stu-id="38147-112">Version</span></span>|<span data-ttu-id="38147-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="38147-113">4.5.2</span></span>|
|<span data-ttu-id="38147-114">Typ</span><span class="sxs-lookup"><span data-stu-id="38147-114">Type</span></span>|<span data-ttu-id="38147-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="38147-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="38147-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="38147-116">Affected APIs</span></span>

-<xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
