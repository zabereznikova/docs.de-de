---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902031"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="3ccbc-101">Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="3ccbc-102">Ab ASP.NET Core 3.0 ist AspNetCoreModule v1 (ANCM) nicht mehr im Windows-Hostingpaket enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="3ccbc-103">ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="3ccbc-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="3ccbc-104">For discussion, see [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ccbc-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3ccbc-105">Version introduced</span></span>

<span data-ttu-id="3ccbc-106">3.0</span><span class="sxs-lookup"><span data-stu-id="3ccbc-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3ccbc-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="3ccbc-107">Old behavior</span></span>

<span data-ttu-id="3ccbc-108">ANCM v1 war im Windows-Hostingpaket enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3ccbc-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="3ccbc-109">New behavior</span></span>

<span data-ttu-id="3ccbc-110">ANCM v1 ist nicht mehr im Windows-Hostingpaket enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3ccbc-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3ccbc-111">Reason for change</span></span>

<span data-ttu-id="3ccbc-112">ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ccbc-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3ccbc-113">Recommended action</span></span>

<span data-ttu-id="3ccbc-114">Verwenden Sie ANCM v2 mit ASP.NET Core 3.0-Apps.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="3ccbc-115">Wenn ANCM v1 erforderlich ist, kann es mit dem Windows-Hostingpaket für ASP.NET Core 2.1 oder 2.2 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="3ccbc-116">Diese Änderung stellt einen Breaking Change für ASP.NET Core 3.0-Apps dar, für die Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="3ccbc-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="3ccbc-117">Sie verwenden ANCM v1 explizit über `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="3ccbc-118">Sie verfügen über eine benutzerdefinierte Datei *web.config*  mit `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="3ccbc-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="3ccbc-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3ccbc-119">Category</span></span>

<span data-ttu-id="3ccbc-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ccbc-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ccbc-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3ccbc-121">Affected APIs</span></span>

<span data-ttu-id="3ccbc-122">Keine</span><span class="sxs-lookup"><span data-stu-id="3ccbc-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
