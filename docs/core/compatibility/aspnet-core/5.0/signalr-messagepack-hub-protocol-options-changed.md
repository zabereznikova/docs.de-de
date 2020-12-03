---
title: 'Breaking Change: SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b75dbec834699472f18b3058052274476bd9751d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759550"
---
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="2e036-103">SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert</span><span class="sxs-lookup"><span data-stu-id="2e036-103">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="2e036-104">Der Optionstyp für das SignalR-MessagePack-Hubprotokoll in ASP.NET Core wurde von `IList<MessagePack.IFormatterResolver>` in den [MessagePack](https://www.nuget.org/packages/MessagePack)-`MessagePackSerializerOptions`-Typ der Bibliothek geändert.</span><span class="sxs-lookup"><span data-stu-id="2e036-104">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="2e036-105">Diese Änderung wird unter [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506) behandelt.</span><span class="sxs-lookup"><span data-stu-id="2e036-105">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2e036-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2e036-106">Version introduced</span></span>

<span data-ttu-id="2e036-107">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="2e036-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="2e036-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="2e036-108">Old behavior</span></span>

<span data-ttu-id="2e036-109">Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2e036-109">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="2e036-110">Folgendermaßen können Sie Optionen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="2e036-110">And replace the options as follows:</span></span>

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

## <a name="new-behavior"></a><span data-ttu-id="2e036-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="2e036-111">New behavior</span></span>

<span data-ttu-id="2e036-112">Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2e036-112">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="2e036-113">Folgendermaßen können Sie Optionen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="2e036-113">And replace the options as follows:</span></span>

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

## <a name="reason-for-change"></a><span data-ttu-id="2e036-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="2e036-114">Reason for change</span></span>

<span data-ttu-id="2e036-115">Diese Änderung ist Teil der Umstellung auf MessagePack 2.x, die unter [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404) angekündigt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e036-115">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="2e036-116">Der Bibliothek von Version 2.x wurde eine Options-API hinzugefügt, die einfacher zu verwenden ist und mehr Features als die zuvor verfügbare `MessagePack.IFormatterResolver`-Liste bietet.</span><span class="sxs-lookup"><span data-stu-id="2e036-116">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2e036-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="2e036-117">Recommended action</span></span>

<span data-ttu-id="2e036-118">Dieser Breaking Change wirkt sich auf alle Benutzer aus, die Werte in <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2e036-118">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="2e036-119">Wenn Sie das SignalR-MessagePack-Hubprotokoll in ASP.NET Core verwenden und die Optionen ändern, stellen Sie sicher, dass die neue Options-API wie oben veranschaulicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e036-119">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2e036-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2e036-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
