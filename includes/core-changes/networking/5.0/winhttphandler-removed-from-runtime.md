---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608461"
---
### <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="32580-101">Entfernung von WinHttpHandler aus der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="32580-101">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="32580-102">Die `WinHttpHandler`-Klasse wurde aus der Assembly *System.Net.Http.dll* entfernt.</span><span class="sxs-lookup"><span data-stu-id="32580-102">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="32580-103">Sie ist jetzt nur als [OOB-NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) (Out-of-Band) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32580-103">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32580-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="32580-104">Version introduced</span></span>

<span data-ttu-id="32580-105">5.0</span><span class="sxs-lookup"><span data-stu-id="32580-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="32580-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="32580-106">Change description</span></span>

<span data-ttu-id="32580-107">In früheren .NET-Versionen ist die <xref:System.Net.Http.WinHttpHandler>-Klasse als Teil der .NET-Kernbibliotheken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32580-107">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="32580-108">Ab .NET 5.0 ist die <xref:System.Net.Http.WinHttpHandler>-Klasse nur als separat installiertes [NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32580-108">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32580-109">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="32580-109">Recommended action</span></span>

<span data-ttu-id="32580-110">Installieren Sie das [NuGet-Paket „System.Net.Http.WinHttpHandler“](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="32580-110">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="32580-111">Wenn Sie keine WinHTTP-spezifischen Features benötigen, können Sie stattdessen <xref:System.Net.Http.SocketsHttpHandler> verwenden.</span><span class="sxs-lookup"><span data-stu-id="32580-111">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

#### <a name="category"></a><span data-ttu-id="32580-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="32580-112">Category</span></span>

<span data-ttu-id="32580-113">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="32580-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32580-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="32580-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
