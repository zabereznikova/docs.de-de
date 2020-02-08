---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920641"
---

<span data-ttu-id="a0a6e-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="a0a6e-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="a0a6e-102">**product**</span></span>\
<span data-ttu-id="a0a6e-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-103">The type of .NET product to install.</span></span> <span data-ttu-id="a0a6e-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a0a6e-104">Valid options are:</span></span>

  - <span data-ttu-id="a0a6e-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="a0a6e-105">dotnet</span></span>
  - <span data-ttu-id="a0a6e-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="a0a6e-106">aspnetcore</span></span>

- <span data-ttu-id="a0a6e-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a0a6e-107">**type**</span></span>\
<span data-ttu-id="a0a6e-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="a0a6e-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a0a6e-109">Valid options are:</span></span>

  - <span data-ttu-id="a0a6e-110">SDK</span><span class="sxs-lookup"><span data-stu-id="a0a6e-110">sdk</span></span>
  - <span data-ttu-id="a0a6e-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a0a6e-111">runtime</span></span>

- <span data-ttu-id="a0a6e-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="a0a6e-112">**version**</span></span>\
<span data-ttu-id="a0a6e-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="a0a6e-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="a0a6e-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="a0a6e-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="a0a6e-116">3.0</span><span class="sxs-lookup"><span data-stu-id="a0a6e-116">3.0</span></span>
  - <span data-ttu-id="a0a6e-117">2.2</span><span class="sxs-lookup"><span data-stu-id="a0a6e-117">2.2</span></span>
  - <span data-ttu-id="a0a6e-118">2.1</span><span class="sxs-lookup"><span data-stu-id="a0a6e-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="a0a6e-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a0a6e-119">Examples</span></span>

- <span data-ttu-id="a0a6e-120">Installieren des .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="a0a6e-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="a0a6e-121">Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="a0a6e-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="a0a6e-122">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="a0a6e-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="a0a6e-123">Fehlendes Paket</span><span class="sxs-lookup"><span data-stu-id="a0a6e-123">Package missing</span></span>

<span data-ttu-id="a0a6e-124">Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-124">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="a0a6e-125">Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="a0a6e-126">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="a0a6e-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span>
