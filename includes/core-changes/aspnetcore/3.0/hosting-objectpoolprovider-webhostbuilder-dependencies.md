---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032523"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="459cb-101">Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt.</span><span class="sxs-lookup"><span data-stu-id="459cb-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="459cb-102">Um ASP.NET Core produktiver zu machen, wurde der `ObjectPoolProvider` aus dem Hauptsatz von Abhängigkeiten entfernt.</span><span class="sxs-lookup"><span data-stu-id="459cb-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="459cb-103">Bestimmte Komponenten, die von `ObjectPoolProvider` abhängen, fügen sich jetzt selbst hinzu.</span><span class="sxs-lookup"><span data-stu-id="459cb-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="459cb-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span><span class="sxs-lookup"><span data-stu-id="459cb-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="459cb-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="459cb-105">Version introduced</span></span>

<span data-ttu-id="459cb-106">3.0</span><span class="sxs-lookup"><span data-stu-id="459cb-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="459cb-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="459cb-107">Old behavior</span></span>

<span data-ttu-id="459cb-108">`WebHostBuilder` hat `ObjectPoolProvider` standardmäßig im Container für Abhängigkeitsinjektionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="459cb-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="459cb-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="459cb-109">New behavior</span></span>

<span data-ttu-id="459cb-110">`WebHostBuilder` stellt `ObjectPoolProvider` nicht mehr standardmäßig im Container für Abhängigkeitsinjektionen bereit.</span><span class="sxs-lookup"><span data-stu-id="459cb-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="459cb-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="459cb-111">Reason for change</span></span>

<span data-ttu-id="459cb-112">Diese Änderung wurde vorgenommen, um ASP.NET Core produktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="459cb-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="459cb-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="459cb-113">Recommended action</span></span>

<span data-ttu-id="459cb-114">Wenn die Komponente `ObjectPoolProvider` erfordert, muss sie Ihren Abhängigkeiten über die `IServiceCollection` hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="459cb-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="459cb-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="459cb-115">Category</span></span>

<span data-ttu-id="459cb-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="459cb-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="459cb-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="459cb-117">Affected APIs</span></span>

<span data-ttu-id="459cb-118">Keine</span><span class="sxs-lookup"><span data-stu-id="459cb-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
