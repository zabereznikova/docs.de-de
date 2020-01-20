---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901660"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="8cfaa-101">Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="8cfaa-102">Die einzigen Typen, die vom generischen Host für Konstruktorinjektionen der `Startup`-Klasse unterstützt werden, sind `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="8cfaa-103">Apps, die `WebHost` verwenden, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8cfaa-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8cfaa-104">Change description</span></span>

<span data-ttu-id="8cfaa-105">Vor ASP.NET Core 3.0 konnte die Konstruktorinjektion für beliebige Typen im Konstruktor der `Startup`-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="8cfaa-106">In ASP.NET Core 3.0 wurde der Webstapel der Bibliothek des generischen Hosts zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="8cfaa-107">Sie können die Änderung in der Datei *Program.cs*  der Vorlagen sehen:</span><span class="sxs-lookup"><span data-stu-id="8cfaa-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="8cfaa-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="8cfaa-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="8cfaa-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="8cfaa-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="8cfaa-110">`Host` verwendet einen Container zur Abhängigkeitsinjektion, um die App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="8cfaa-111">`WebHost` verwendet zwei Container: einen für den Host und einen für die App.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="8cfaa-112">Daher unterstützt der `Startup`-Konstruktor keine benutzerdefinierte Dienstinjektion mehr.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="8cfaa-113">Es können nur `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="8cfaa-114">Diese Änderung verhindert Probleme mit Abhängigkeitsinjektionen, z. B. die doppelte Erstellung eines Singletondiensts.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8cfaa-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8cfaa-115">Version introduced</span></span>

<span data-ttu-id="8cfaa-116">3.0</span><span class="sxs-lookup"><span data-stu-id="8cfaa-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8cfaa-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="8cfaa-117">Reason for change</span></span>

<span data-ttu-id="8cfaa-118">Diese Änderung ist eine Folge der geänderten Zuordnung des Webstapels zur Bibliothek des generischen Hosts.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8cfaa-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="8cfaa-119">Recommended action</span></span>

<span data-ttu-id="8cfaa-120">Fügen Sie Dienste in die Signatur der `Startup.Configure`-Methode ein.</span><span class="sxs-lookup"><span data-stu-id="8cfaa-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="8cfaa-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cfaa-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="8cfaa-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8cfaa-122">Category</span></span>

<span data-ttu-id="8cfaa-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8cfaa-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8cfaa-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8cfaa-124">Affected APIs</span></span>

<span data-ttu-id="8cfaa-125">Keine</span><span class="sxs-lookup"><span data-stu-id="8cfaa-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
