---
ms.openlocfilehash: 7723892a33bf7dd8e475b2f696db5d9ab287e182
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602753"
---

<span data-ttu-id="59a13-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="59a13-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="59a13-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="59a13-102">**product**</span></span>\
<span data-ttu-id="59a13-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="59a13-103">The type of .NET product to install.</span></span> <span data-ttu-id="59a13-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="59a13-104">Valid options are:</span></span>

  - <span data-ttu-id="59a13-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="59a13-105">dotnet</span></span>
  - <span data-ttu-id="59a13-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="59a13-106">aspnetcore</span></span>

- <span data-ttu-id="59a13-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="59a13-107">**type**</span></span>\
<span data-ttu-id="59a13-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="59a13-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="59a13-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="59a13-109">Valid options are:</span></span>

  - <span data-ttu-id="59a13-110">SDK</span><span class="sxs-lookup"><span data-stu-id="59a13-110">sdk</span></span>
  - <span data-ttu-id="59a13-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="59a13-111">runtime</span></span>

- <span data-ttu-id="59a13-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="59a13-112">**version**</span></span>\
<span data-ttu-id="59a13-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="59a13-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="59a13-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="59a13-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="59a13-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="59a13-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="59a13-116">3.1</span><span class="sxs-lookup"><span data-stu-id="59a13-116">3.1</span></span>
  - <span data-ttu-id="59a13-117">3.0</span><span class="sxs-lookup"><span data-stu-id="59a13-117">3.0</span></span>
  - <span data-ttu-id="59a13-118">2.1</span><span class="sxs-lookup"><span data-stu-id="59a13-118">2.1</span></span>

  <span data-ttu-id="59a13-119">Es ist möglich, dass das SDK bzw. die Runtime, das/die Sie herunterladen möchten, für Ihre Linux-Distribution nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59a13-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="59a13-120">Eine Liste der unterstützten Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="59a13-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="59a13-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="59a13-121">Examples</span></span>

- <span data-ttu-id="59a13-122">Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="59a13-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="59a13-123">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="59a13-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="59a13-124">Installieren des .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="59a13-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="59a13-125">Fehlendes Paket</span><span class="sxs-lookup"><span data-stu-id="59a13-125">Package missing</span></span>

<span data-ttu-id="59a13-126">Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59a13-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="59a13-127">Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="59a13-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="59a13-128">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="59a13-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="59a13-129">Eine Liste der von .NET Core unterstützten Linux-Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="59a13-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../linux.md).</span></span>
