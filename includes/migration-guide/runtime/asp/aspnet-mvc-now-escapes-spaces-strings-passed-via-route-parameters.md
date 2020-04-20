---
ms.openlocfilehash: 7444ddbdd4a7c5f731fba8528ee2334374fc254e
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275118"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="f04a0-101">ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="f04a0-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f04a0-102">Details</span><span class="sxs-lookup"><span data-stu-id="f04a0-102">Details</span></span>|<span data-ttu-id="f04a0-103">Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="f04a0-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="f04a0-104">Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.</span><span class="sxs-lookup"><span data-stu-id="f04a0-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="f04a0-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f04a0-105">Suggestion</span></span>|<span data-ttu-id="f04a0-106">Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f04a0-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="f04a0-107">Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f04a0-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="f04a0-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="f04a0-108">Scope</span></span>|<span data-ttu-id="f04a0-109">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="f04a0-109">Minor</span></span>|
|<span data-ttu-id="f04a0-110">Version</span><span class="sxs-lookup"><span data-stu-id="f04a0-110">Version</span></span>|<span data-ttu-id="f04a0-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f04a0-111">4.5.2</span></span>|
|<span data-ttu-id="f04a0-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f04a0-112">Type</span></span>|<span data-ttu-id="f04a0-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f04a0-113">Runtime</span></span>|
|<span data-ttu-id="f04a0-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f04a0-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
