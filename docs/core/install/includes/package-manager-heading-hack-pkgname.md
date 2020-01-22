---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116148"
---

<span data-ttu-id="828e2-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="828e2-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="828e2-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="828e2-102">**product**</span></span>\
<span data-ttu-id="828e2-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="828e2-103">The type of .NET product to install.</span></span> <span data-ttu-id="828e2-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="828e2-104">Valid options are:</span></span>

  - <span data-ttu-id="828e2-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="828e2-105">dotnet</span></span>
  - <span data-ttu-id="828e2-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="828e2-106">aspnetcore</span></span>

- <span data-ttu-id="828e2-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="828e2-107">**type**</span></span>\
<span data-ttu-id="828e2-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="828e2-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="828e2-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="828e2-109">Valid options are:</span></span>

  - <span data-ttu-id="828e2-110">SDK</span><span class="sxs-lookup"><span data-stu-id="828e2-110">sdk</span></span>
  - <span data-ttu-id="828e2-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="828e2-111">runtime</span></span>

- <span data-ttu-id="828e2-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="828e2-112">**version**</span></span>\
<span data-ttu-id="828e2-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="828e2-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="828e2-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="828e2-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="828e2-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="828e2-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="828e2-116">3.0</span><span class="sxs-lookup"><span data-stu-id="828e2-116">3.0</span></span>
  - <span data-ttu-id="828e2-117">2.2</span><span class="sxs-lookup"><span data-stu-id="828e2-117">2.2</span></span>
  - <span data-ttu-id="828e2-118">2.1</span><span class="sxs-lookup"><span data-stu-id="828e2-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="828e2-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="828e2-119">Examples</span></span>

- <span data-ttu-id="828e2-120">Installieren des .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="828e2-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="828e2-121">Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="828e2-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="828e2-122">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="828e2-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="828e2-123">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="828e2-123">Troubleshoot</span></span>

<span data-ttu-id="828e2-124">Wenn die Paketkombination nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="828e2-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="828e2-125">Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="828e2-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="828e2-126">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="828e2-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
