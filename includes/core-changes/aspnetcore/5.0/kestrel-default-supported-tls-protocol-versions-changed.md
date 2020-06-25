---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803241"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Kestrel: Standardmäßig unterstützte TLS-Protokollversionen geändert

Kestrel verwendet jetzt die Standard-TLS-Protokollversionen des Systems, anstatt Verbindungen mit den TLS 1.1- und TLS 1.2-Protokollen wie bisher einzuschränken.

Diese Änderung ermöglicht Folgendes:

* TLS 1.3 wird standardmäßig in Umgebungen verwendet, die diese unterstützen.
* TLS 1.0 wird in einigen Umgebungen wie Windows Server 2016 (Standard) verwendet, was üblicherweise [nicht wünschenswert](/security/engineering/solving-tls1-problem) ist.

Weitere Informationen finden Sie unter dem Issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).

#### <a name="version-introduced"></a>Eingeführt in Version

Version 5.0 Vorschau 6

#### <a name="old-behavior"></a>Altes Verhalten

Kestrel erforderte, dass Verbindungen standardmäßig TLS 1.1 oder TLS 1.2 verwenden.

#### <a name="new-behavior"></a>Neues Verhalten

Kestrel ermöglicht dem Betriebssystem, das am besten geeignete Protokoll auszuwählen und unsichere Protokolle zu blockieren. Der Standardwert für <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> ist nun `SslProtocols.None` statt `SslProtocols.Tls12 | SslProtocols.Tls11`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung sollte bewirken, dass TLS 1.3 und zukünftige TLS-Versionen standardmäßig unterstützt werden, sobald sie verfügbar sind.

#### <a name="recommended-action"></a>Empfohlene Aktion

Sofern in Ihrer Anwendung kein bestimmter Grund dagegen besteht, sollten Sie die neuen Standardwerte verwenden. Vergewissern Sie sich, dass Ihr System so konfiguriert ist, dass nur sichere Protokolle zulässig sind.

Führen Sie eine der folgenden Aktionen durch, um ältere Protokolle zu deaktivieren:

* Deaktivieren Sie ältere Protokolle wie TLS 1.0 systemweit mithilfe der [Anweisungen für Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry). Diese sind derzeit in allen Windows-Versionen standardmäßig aktiviert.
* Wählen Sie die Protokolle, die Sie im Code unterstützen möchten, manuell wie folgt aus:

    ```csharp
    using System.Security.Authentication;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

Leider gibt es keine API zum Ausschließen bestimmter Protokolle.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
