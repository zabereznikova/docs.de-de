---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032603"
---
### <a name="logging-debuglogger-class-made-internal"></a><span data-ttu-id="5cc6f-101">Protokollieren: DebugLogger-Klasse als „internal“ deklariert</span><span class="sxs-lookup"><span data-stu-id="5cc6f-101">Logging: DebugLogger class made internal</span></span>

<span data-ttu-id="5cc6f-102">Vor ASP.NET Core 3.0 war `public` Zugriffsmodifizierer von `DebugLogger`.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-102">Prior to ASP.NET Core 3.0, `DebugLogger`'s access modifier was `public`.</span></span> <span data-ttu-id="5cc6f-103">In ASP.NET Core 3.0 wurde der Zugriffsmodifizierer in `internal` geändert.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-103">In ASP.NET Core 3.0, the access modifier changed to `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5cc6f-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5cc6f-104">Version introduced</span></span>

<span data-ttu-id="5cc6f-105">3.0</span><span class="sxs-lookup"><span data-stu-id="5cc6f-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5cc6f-106">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5cc6f-106">Reason for change</span></span>

<span data-ttu-id="5cc6f-107">Die Änderung erfolgt aus folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="5cc6f-107">The change is being made to:</span></span>

* <span data-ttu-id="5cc6f-108">Erzwingen von Konsistenz mit anderen Protokollierungsimplementierungen, z. B. `ConsoleLogger`</span><span class="sxs-lookup"><span data-stu-id="5cc6f-108">Enforce consistency with other logger implementations such as `ConsoleLogger`.</span></span>
* <span data-ttu-id="5cc6f-109">Reduzieren der API-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="5cc6f-109">Reduce the API surface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5cc6f-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5cc6f-110">Recommended action</span></span>

<span data-ttu-id="5cc6f-111">Verwenden Sie die <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder`-Erweiterungsmethode, um die Debugprotokollierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-111">Use the <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` extension method to enable debug logging.</span></span> <span data-ttu-id="5cc6f-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> ist auch weiterhin `public`, wenn der Dienst manuell registriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> is also still `public` in the event the service needs to be registered manually.</span></span>

#### <a name="category"></a><span data-ttu-id="5cc6f-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5cc6f-113">Category</span></span>

<span data-ttu-id="5cc6f-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5cc6f-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5cc6f-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5cc6f-115">Affected APIs</span></span>

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
