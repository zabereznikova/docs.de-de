---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803240"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="fc229-101">ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="fc229-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fc229-102">Details</span><span class="sxs-lookup"><span data-stu-id="fc229-102">Details</span></span>|<span data-ttu-id="fc229-103">Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="fc229-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="fc229-104">Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.</span><span class="sxs-lookup"><span data-stu-id="fc229-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="fc229-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fc229-105">Suggestion</span></span>|<span data-ttu-id="fc229-106">Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fc229-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="fc229-107">Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="fc229-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="fc229-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="fc229-108">Scope</span></span>|<span data-ttu-id="fc229-109">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="fc229-109">Minor</span></span>|
|<span data-ttu-id="fc229-110">Version</span><span class="sxs-lookup"><span data-stu-id="fc229-110">Version</span></span>|<span data-ttu-id="fc229-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="fc229-111">4.5.2</span></span>|
|<span data-ttu-id="fc229-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fc229-112">Type</span></span>|<span data-ttu-id="fc229-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fc229-113">Runtime</span></span>|
|<span data-ttu-id="fc229-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fc229-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
