---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998798"
---

<span data-ttu-id="71dc5-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="71dc5-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="71dc5-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="71dc5-102">**product**</span></span>\
<span data-ttu-id="71dc5-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="71dc5-103">The type of .NET product to install.</span></span> <span data-ttu-id="71dc5-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="71dc5-104">Valid options are:</span></span>

  - <span data-ttu-id="71dc5-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="71dc5-105">dotnet</span></span>
  - <span data-ttu-id="71dc5-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="71dc5-106">aspnetcore</span></span>

- <span data-ttu-id="71dc5-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="71dc5-107">**type**</span></span>\
<span data-ttu-id="71dc5-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="71dc5-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="71dc5-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="71dc5-109">Valid options are:</span></span>

  - <span data-ttu-id="71dc5-110">SDK</span><span class="sxs-lookup"><span data-stu-id="71dc5-110">sdk</span></span>
  - <span data-ttu-id="71dc5-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="71dc5-111">runtime</span></span>

- <span data-ttu-id="71dc5-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="71dc5-112">**version**</span></span>\
<span data-ttu-id="71dc5-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="71dc5-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="71dc5-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="71dc5-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="71dc5-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="71dc5-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="71dc5-116">3.0</span><span class="sxs-lookup"><span data-stu-id="71dc5-116">3.0</span></span>
  - <span data-ttu-id="71dc5-117">2.2</span><span class="sxs-lookup"><span data-stu-id="71dc5-117">2.2</span></span>
  - <span data-ttu-id="71dc5-118">2.1</span><span class="sxs-lookup"><span data-stu-id="71dc5-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="71dc5-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="71dc5-119">Examples</span></span>

- <span data-ttu-id="71dc5-120">Installieren des .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="71dc5-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="71dc5-121">Installieren der ASP.NET Core 3.0-Runtime: `aspnetcore-runtime-3.0`</span><span class="sxs-lookup"><span data-stu-id="71dc5-121">Install the ASP.NET Core 3.0 runtime: `aspnetcore-runtime-3.0`</span></span>
- <span data-ttu-id="71dc5-122">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="71dc5-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="71dc5-123">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="71dc5-123">Troubleshoot</span></span>

<span data-ttu-id="71dc5-124">Wenn die Paketkombination nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71dc5-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="71dc5-125">Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="71dc5-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="71dc5-126">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="71dc5-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
