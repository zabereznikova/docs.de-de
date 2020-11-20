---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506862"
---

<span data-ttu-id="3b195-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="3b195-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="3b195-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="3b195-102">**product**</span></span>\
<span data-ttu-id="3b195-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="3b195-103">The type of .NET product to install.</span></span> <span data-ttu-id="3b195-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="3b195-104">Valid options are:</span></span>

  - <span data-ttu-id="3b195-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="3b195-105">dotnet</span></span>
  - <span data-ttu-id="3b195-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="3b195-106">aspnetcore</span></span>

- <span data-ttu-id="3b195-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3b195-107">**type**</span></span>\
<span data-ttu-id="3b195-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="3b195-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="3b195-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="3b195-109">Valid options are:</span></span>

  - <span data-ttu-id="3b195-110">SDK</span><span class="sxs-lookup"><span data-stu-id="3b195-110">sdk</span></span>
  - <span data-ttu-id="3b195-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3b195-111">runtime</span></span>

- <span data-ttu-id="3b195-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="3b195-112">**version**</span></span>\
<span data-ttu-id="3b195-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="3b195-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="3b195-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="3b195-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="3b195-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="3b195-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="3b195-116">5.0</span><span class="sxs-lookup"><span data-stu-id="3b195-116">5.0</span></span>
  - <span data-ttu-id="3b195-117">3.1</span><span class="sxs-lookup"><span data-stu-id="3b195-117">3.1</span></span>
  - <span data-ttu-id="3b195-118">3.0</span><span class="sxs-lookup"><span data-stu-id="3b195-118">3.0</span></span>
  - <span data-ttu-id="3b195-119">2.1</span><span class="sxs-lookup"><span data-stu-id="3b195-119">2.1</span></span>

  <span data-ttu-id="3b195-120">Es ist möglich, dass das SDK bzw. die Runtime, das/die Sie herunterladen möchten, für Ihre Linux-Distribution nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3b195-120">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="3b195-121">Eine Liste der unterstützten Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="3b195-121">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="3b195-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3b195-122">Examples</span></span>

- <span data-ttu-id="3b195-123">Installieren der ASP.NET Core 5.0-Runtime: `aspnetcore-runtime-5.0`</span><span class="sxs-lookup"><span data-stu-id="3b195-123">Install the ASP.NET Core 5.0 runtime: `aspnetcore-runtime-5.0`</span></span>
- <span data-ttu-id="3b195-124">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="3b195-124">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="3b195-125">Installieren des .NET 5.0 SDK: `dotnet-sdk-5.0`</span><span class="sxs-lookup"><span data-stu-id="3b195-125">Install the .NET 5.0 SDK: `dotnet-sdk-5.0`</span></span>
- <span data-ttu-id="3b195-126">Installieren des .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="3b195-126">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="3b195-127">Fehlendes Paket</span><span class="sxs-lookup"><span data-stu-id="3b195-127">Package missing</span></span>

<span data-ttu-id="3b195-128">Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b195-128">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="3b195-129">Beispielsweise gibt es kein ASP.NET Core SDK, die SDK-Komponenten sind im .NET SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b195-129">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET SDK.</span></span> <span data-ttu-id="3b195-130">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="3b195-130">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="3b195-131">Eine Liste der von .NET Core unterstützten Linux-Distributionen finden Sie unter [.NET-Abhängigkeiten und -Anforderungen](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="3b195-131">For a list of Linux distributions supported by .NET Core, see [.NET dependencies and requirements](../linux.md).</span></span>
