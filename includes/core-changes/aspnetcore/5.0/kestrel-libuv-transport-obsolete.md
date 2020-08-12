---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474376"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a>Kestrel: Markierung von libuv-Transport als veraltet

Frühere Versionen von ASP.NET Core haben Libuv als Implementierungsdetail für die Ausführung der asynchronen Ein- und Ausgabe verwendet. In ASP.NET Core 2.0 wurde ein alternativer <xref:System.Net.Sockets.Socket>-basierter Transport entwickelt. In ASP.NET Core 2.1 wurde Kestrel standardmäßig auf die Verwendung des `Socket`-basierten Transports umgestellt. Die Unterstützung von Libuv wurde aus Kompatibilitätsgründen beibehalten.

Heute ist die Verwendung des `Socket`-basierten Transports weitaus häufiger als des Libuv-Transports. Folglich ist die Libuv-Unterstützung in .NET 5.0 als veraltet markiert und wird in .NET 6.0 vollständig entfernt.

Im Rahmen dieser Änderung wird die Libuv-Unterstützung für neue Betriebssystemplattformen (wie Windows ARM64) nicht im .NET 5.0-Zeitrahmen hinzugefügt.

Informationen zu Blockierungsproblemen, die die Verwendung des Libuv-Transports erfordern, finden Sie im GitHub Issue unter [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="old-behavior"></a>Altes Verhalten

Die Libuv-APIs sind nicht als veraltet markiert.

#### <a name="new-behavior"></a>Neues Verhalten

Die Libuv-APIs sind als veraltet markiert.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der `Socket`-basierte Transport ist die Standardeinstellung. Es gibt keine überzeugenden Gründe, den Libuv-Transport weiterhin zu verwenden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Beenden Sie die Verwendung des [Libuv-Pakets](https://www.nuget.org/packages/Libuv) und der Erweiterungsmethoden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- [WebHostBuilderLibuvExtensions](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [WebHostBuilderLibuvExtensions.UseLibuv](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
