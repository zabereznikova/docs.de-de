---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394304"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="1f7e1-101">Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="1f7e1-102">Die einzigen Typen, die vom generischen Host für Konstruktorinjektionen der `Startup`-Klasse unterstützt werden, sind `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="1f7e1-103">Apps, die `WebHost` verwenden, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1f7e1-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1f7e1-104">Change description</span></span>

<span data-ttu-id="1f7e1-105">Vor ASP.NET Core 3.0 konnte die Konstruktorinjektion für beliebige Typen im Konstruktor der `Startup`-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="1f7e1-106">In ASP.NET Core 3.0 wurde der Webstapel der Bibliothek des generischen Hosts zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="1f7e1-107">Sie können die Änderung in der Datei *Program.cs*  der Vorlagen sehen:</span><span class="sxs-lookup"><span data-stu-id="1f7e1-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="1f7e1-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="1f7e1-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="1f7e1-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="1f7e1-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="1f7e1-110">`Host` verwendet einen Container zur Abhängigkeitsinjektion, um die App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="1f7e1-111">`WebHost` verwendet zwei Container: einen für den Host und einen für die App.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="1f7e1-112">Daher unterstützt der `Startup`-Konstruktor keine benutzerdefinierte Dienstinjektion mehr.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="1f7e1-113">Es können nur `IHostEnvironment`, `IWebHostEnvironment` und `IConfiguration` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="1f7e1-114">Diese Änderung verhindert Probleme mit Abhängigkeitsinjektionen, z. B. die doppelte Erstellung eines Singletondiensts.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1f7e1-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1f7e1-115">Version introduced</span></span>

<span data-ttu-id="1f7e1-116">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7e1-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1f7e1-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1f7e1-117">Reason for change</span></span>

<span data-ttu-id="1f7e1-118">Diese Änderung ist eine Folge der geänderten Zuordnung des Webstapels zur Bibliothek des generischen Hosts.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1f7e1-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="1f7e1-119">Recommended action</span></span>

<span data-ttu-id="1f7e1-120">Fügen Sie Dienste in die Signatur der `Startup.Configure`-Methode ein.</span><span class="sxs-lookup"><span data-stu-id="1f7e1-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="1f7e1-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f7e1-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="1f7e1-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1f7e1-122">Category</span></span>

<span data-ttu-id="1f7e1-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1f7e1-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f7e1-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1f7e1-124">Affected APIs</span></span>

<span data-ttu-id="1f7e1-125">Keine</span><span class="sxs-lookup"><span data-stu-id="1f7e1-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
