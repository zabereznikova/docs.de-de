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
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert

Der Optionstyp für das SignalR-MessagePack-Hubprotokoll in ASP.NET Core wurde von `IList<MessagePack.IFormatterResolver>` in den [MessagePack](https://www.nuget.org/packages/MessagePack)-`MessagePackSerializerOptions`-Typ der Bibliothek geändert.

Diese Änderung wird unter [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 4

## <a name="old-behavior"></a>Altes Verhalten

Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

Folgendermaßen können Sie Optionen ersetzen:

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

## <a name="new-behavior"></a>Neues Verhalten

Sie können den Optionen wie im folgenden Beispiel gezeigt Elemente hinzufügen:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

Folgendermaßen können Sie Optionen ersetzen:

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

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ist Teil der Umstellung auf MessagePack 2.x, die unter [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404) angekündigt wurde. Der Bibliothek von Version 2.x wurde eine Options-API hinzugefügt, die einfacher zu verwenden ist und mehr Features als die zuvor verfügbare `MessagePack.IFormatterResolver`-Liste bietet.

## <a name="recommended-action"></a>Empfohlene Aktion

Dieser Breaking Change wirkt sich auf alle Benutzer aus, die Werte in <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> konfigurieren. Wenn Sie das SignalR-MessagePack-Hubprotokoll in ASP.NET Core verwenden und die Optionen ändern, stellen Sie sicher, dass die neue Options-API wie oben veranschaulicht verwendet wird.

## <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
