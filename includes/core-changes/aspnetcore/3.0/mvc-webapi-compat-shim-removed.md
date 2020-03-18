---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393903"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="2d80b-101">MVC: Web-API-Kompatibilitätsshim wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="2d80b-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="2d80b-102">Ab ASP.NET Core 3.0 ist das Paket `Microsoft.AspNetCore.Mvc.WebApiCompatShim` nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2d80b-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2d80b-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2d80b-103">Change description</span></span>

<span data-ttu-id="2d80b-104">Das Paket `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) bietet partielle Kompatibilität in ASP.NET Core mit der ASP.NET 4.x-Web-API 2, um die Migration vorhandener Web-API-Implementierungen zu ASP.NET Core zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2d80b-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="2d80b-105">Apps, die WebApiCompatShim verwenden, profitieren jedoch nicht von den API-bezogenen Features der letzten ASP.NET Core-Releases.</span><span class="sxs-lookup"><span data-stu-id="2d80b-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="2d80b-106">Zu diesen Features zählen die verbesserte Generierung von Open API-Spezifikationen, die standardisierte Fehlerbehandlung und die Generierung von Clientcode.</span><span class="sxs-lookup"><span data-stu-id="2d80b-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="2d80b-107">Um die API in 3.0 noch weiter zu optimieren, wurde WebApiCompatShim entfernt.</span><span class="sxs-lookup"><span data-stu-id="2d80b-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="2d80b-108">Vorhandene Apps, die WebApiCompatShim verwenden, sollten zum neueren `[ApiController]`-Modell migriert werden.</span><span class="sxs-lookup"><span data-stu-id="2d80b-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2d80b-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2d80b-109">Version introduced</span></span>

<span data-ttu-id="2d80b-110">3.0</span><span class="sxs-lookup"><span data-stu-id="2d80b-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2d80b-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="2d80b-111">Reason for change</span></span>

<span data-ttu-id="2d80b-112">Das Web-API-Kompatibilitätsshim war ein Migrationstool.</span><span class="sxs-lookup"><span data-stu-id="2d80b-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="2d80b-113">Es beschränkt den Benutzerzugriff auf neue Funktionen, die in ASP.NET Core hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2d80b-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2d80b-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="2d80b-114">Recommended action</span></span>

<span data-ttu-id="2d80b-115">Entfernen Sie alle Verwendungen dieses Shims, und migrieren Sie direkt zu der entsprechenden Funktionalität in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2d80b-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="2d80b-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="2d80b-116">Category</span></span>

<span data-ttu-id="2d80b-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2d80b-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2d80b-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2d80b-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
