---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507080"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="6d25f-101">SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert</span><span class="sxs-lookup"><span data-stu-id="6d25f-101">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="6d25f-102">Der Optionstyp für das SignalR-MessagePack-Hubprotokoll in ASP.NET Core wurde von `IList<MessagePack.IFormatterResolver>` in den [MessagePack](https://www.nuget.org/packages/MessagePack)-`MessagePackSerializerOptions`-Typ der Bibliothek geändert.</span><span class="sxs-lookup"><span data-stu-id="6d25f-102">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="6d25f-103">Diese Änderung wird unter [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506) behandelt.</span><span class="sxs-lookup"><span data-stu-id="6d25f-103">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6d25f-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6d25f-104">Version introduced</span></span>

<span data-ttu-id="6d25f-105">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="6d25f-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6d25f-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="6d25f-106">Old behavior</span></span>

<span data-ttu-id="6d25f-107">Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6d25f-107">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="6d25f-108">Folgendermaßen können Sie Optionen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="6d25f-108">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

#### <a name="new-behavior"></a><span data-ttu-id="6d25f-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="6d25f-109">New behavior</span></span>

<span data-ttu-id="6d25f-110">Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6d25f-110">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="6d25f-111">Folgendermaßen können Sie Optionen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="6d25f-111">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

#### <a name="reason-for-change"></a><span data-ttu-id="6d25f-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="6d25f-112">Reason for change</span></span>

<span data-ttu-id="6d25f-113">Diese Änderung ist Teil der Umstellung auf MessagePack 2.x, die unter [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404) angekündigt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d25f-113">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="6d25f-114">Der Bibliothek von Version 2.x wurde eine Options-API hinzugefügt, die einfacher zu verwenden ist und mehr Features als die zuvor verfügbare `MessagePack.IFormatterResolver`-Liste bietet.</span><span class="sxs-lookup"><span data-stu-id="6d25f-114">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6d25f-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6d25f-115">Recommended action</span></span>

<span data-ttu-id="6d25f-116">Dieser Breaking Change wirkt sich auf alle Benutzer aus, die Werte in <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6d25f-116">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="6d25f-117">Wenn Sie das SignalR-MessagePack-Hubprotokoll in ASP.NET Core verwenden und die Optionen ändern, stellen Sie sicher, dass die neue Options-API wie oben veranschaulicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d25f-117">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

#### <a name="category"></a><span data-ttu-id="6d25f-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6d25f-118">Category</span></span>

<span data-ttu-id="6d25f-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6d25f-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6d25f-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6d25f-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
