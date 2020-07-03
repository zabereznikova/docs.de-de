---
ms.openlocfilehash: 92210f6becb5a5a43893ee0fd51ef51e2ddd7f8d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325206"
---
### <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a>Kestrel: Deaktivierung von HTTP/2 bei inkompatiblen Windows-Versionen über TLS

Es müssen zwei Anforderungen erfüllt sein, um HTTP/2 über TLS (Transport Layer Security) unter Windows zu aktivieren:

- ALPN-Unterstützung (Application-Layer Protocol Negotiation), die ab Windows 8.1 und Windows Server 2012 R2 verfügbar ist
- Eine Reihe von Verschlüsselungen, die mit HTTP/2 kompatibel und ab Windows 10 und Windows Server 2016 verfügbar sind

Daher hat sich das Verhalten von Kestrel bei der Konfiguration von HTTP/2 über TLS wie folgt geändert:

- Downgrade auf `Http1` und Protokollieren einer Meldung auf `Information`-Ebene, wenn [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) auf `Http1AndHttp2` festgelegt ist. Der Standardwert für `ListenOptions.HttpProtocols` lautet `Http1AndHttp2`.
- Ausgabe von `NotSupportedException`, wenn `ListenOptions.HttpProtocols` auf `Http2` festgelegt ist

Weitere Informationen finden Sie unter Issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).

#### <a name="version-introduced"></a>Eingeführt in Version

ASP.NET Core 5.0 Preview 7

#### <a name="old-behavior"></a>Altes Verhalten

In der folgenden Tabelle wird das Verhalten beschrieben, wenn HTTP/2 über TLS konfiguriert ist.

| Protokolle | Windows 7,<br />Windows Server 2008 R2<br />oder früher | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016<br />oder höher |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Ausgabe von `NotSupportedException`                   | Fehler beim TLS-Handshake     | Fehler beim TLS-Handshake &ast;     | Kein Fehler |
| `Http1AndHttp2` | Herabstufung auf `Http1`                    | Herabstufung auf `Http1`     | Fehler beim TLS-Handshake &ast;     | Kein Fehler |

&ast; Konfigurieren Sie kompatible Verschlüsselungssammlungen, um diese Szenarios zu aktivieren.

#### <a name="new-behavior"></a>Neues Verhalten

In der folgenden Tabelle wird das Verhalten beschrieben, wenn HTTP/2 über TLS konfiguriert ist.

| Protokolle | Windows 7,<br />Windows Server 2008 R2<br />oder früher | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016<br />oder höher |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Ausgabe von `NotSupportedException`                   | Ausgabe von `NotSupportedException`     | Ausgabe von `NotSupportedException` &ast;&ast;     | Kein Fehler |
| `Http1AndHttp2` | Downgrade auf `Http1`                    | Downgrade auf `Http1`     | Downgrade auf `Http1` &ast;&ast;     | Kein Fehler |

&ast;&ast; Konfigurieren Sie kompatible Verschlüsselungssammlungen, und legen Sie den App-Kontextwechsel `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` auf `true` fest, um diese Szenarios zu aktivieren.

#### <a name="reason-for-change"></a>Grund für die Änderung

Durch diese Änderung wird sichergestellt, dass Kompatibilitätsfehler bei HTTP/2 über TLS und älteren Windows-Versionen so früh und klar wie möglich angezeigt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Stellen Sie sicher, dass HTTP/2 über TLS bei inkompatiblen Windows-Versionen deaktiviert ist. Windows 8.1 und Windows Server 2012 R2 sind inkompatibel, da sie standardmäßig nicht über die erforderlichen Verschlüsselungen verfügen. Allerdings ist es möglich, die Computerkonfigurationseinstellungen so zu aktualisieren, dass mit HTTP/2 kompatible Verschlüsselungen verwendet werden. Weitere Informationen finden Sie unter [TLS-Verschlüsselungssammlungen in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1). Nach der Konfiguration muss HTTP/2 über TLS in Kestrel aktiviert werden, indem der App-Kontextwechsel `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` festgelegt wird. Zum Beispiel:

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

Die vorhandene Unterstützung wurde nicht geändert. HTTP/2 über TLS hat beispielsweise nie unter Windows 8 oder Windows Server 2012 funktioniert. Durch diese Änderung wird die Anzeige von Fehlern in den nicht unterstützten Szenarios angepasst.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
