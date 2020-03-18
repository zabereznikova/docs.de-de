---
ms.openlocfilehash: 8979b7ffc09726c6588fe3ba60b916202697648f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522684"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="ccf1a-101">SignalR: HubConnectionContext-Konstruktoren wurden geändert.</span><span class="sxs-lookup"><span data-stu-id="ccf1a-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="ccf1a-102">Die `HubConnectionContext`-Konstruktoren von SignalR wurden so geändert, dass sie anstelle von mehreren Parametern einen Optionstyp akzeptieren, damit auch in Zukunft Optionen hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="ccf1a-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="ccf1a-103">Durch diese Änderung werden zwei Konstruktoren durch einen einzelnen Konstruktor ersetzt, der einen Optionstyp akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ccf1a-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ccf1a-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ccf1a-104">Version introduced</span></span>

<span data-ttu-id="ccf1a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="ccf1a-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ccf1a-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ccf1a-106">Old behavior</span></span>

<span data-ttu-id="ccf1a-107">`HubConnectionContext` hatte zwei Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="ccf1a-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="ccf1a-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ccf1a-108">New behavior</span></span>

<span data-ttu-id="ccf1a-109">Die beiden Konstruktoren wurden entfernt und durch einen Konstruktor ersetzt:</span><span class="sxs-lookup"><span data-stu-id="ccf1a-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="ccf1a-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ccf1a-110">Reason for change</span></span>

<span data-ttu-id="ccf1a-111">Der neue Konstruktor verwendet ein neues Optionsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ccf1a-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="ccf1a-112">Aus diesem Grund können die Features von `HubConnectionContext` in Zukunft erweitert werden, ohne dass weitere Konstruktoren erforderlich werden oder Breaking Changes vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccf1a-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ccf1a-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ccf1a-113">Recommended action</span></span>

<span data-ttu-id="ccf1a-114">Verwenden Sie anstelle der folgenden Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="ccf1a-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="ccf1a-115">den folgenden Konstruktor:</span><span class="sxs-lookup"><span data-stu-id="ccf1a-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="ccf1a-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ccf1a-116">Category</span></span>

<span data-ttu-id="ccf1a-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ccf1a-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ccf1a-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ccf1a-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
