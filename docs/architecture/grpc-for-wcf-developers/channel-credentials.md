---
title: 'Channel-Anmelde Informationen: GrpC für WCF-Entwickler'
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-channelanmelde Informationen in ASP.net Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: b424db49337a2dc6e3d0245d36349e3f408cdf6c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967960"
---
# <a name="channel-credentials"></a>Anmeldeinformationen für den Kanal

Wie der Name schon sagt, werden Channel-Anmelde Informationen an den zugrunde liegenden GrpC-Kanal angefügt. Die Standardform der channelanmelde Informationen verwendet die Client Zertifikat Authentifizierung, bei der der Client beim Herstellen der Verbindung ein TLS-Zertifikat bereitstellt, das vom Server überprüft wird, bevor Aufrufe zugelassen werden.

Channelanmeldeinformationen können mit Anmelde Informationen kombiniert werden, um eine umfassende Sicherheit für einen GrpC-Dienst bereitzustellen. Die channelanmeldeinformationen belegen, dass die Client Anwendung auf den Dienst zugreifen darf, und die Anmelde Informationen des Benutzers enthalten Informationen über die Person, die die Client Anwendung verwendet.

Die Client Zertifikat Authentifizierung funktioniert für GrpC auf die gleiche Weise wie für ASP.net Core. Der Konfigurations Vorgang wird hier zusammengefasst, aber weitere Informationen finden Sie im Artikel [Konfigurieren der Zertifikat Authentifizierung in ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .

Für Entwicklungszwecke können Sie ein selbst signiertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle signiert wurde.

## <a name="adding-certificate-authentication-to-the-server"></a>Hinzufügen der Zertifikat Authentifizierung zum Server

Sie müssen die Zertifikat Authentifizierung auf Hostebene konfigurieren, z. b. auf dem Kestrel-Server und in der ASP.net Core Pipeline.

### <a name="configuring-certificate-validation-on-kestrel"></a>Konfigurieren der Zertifikat Überprüfung für Kestrel

Sie können Kestrel (den ASP.net Core http-Server) so konfigurieren, dass ein Client Zertifikat erforderlich ist. Optional können Sie auch eine Überprüfung des angegebenen Zertifikats ausführen, bevor Sie eingehende Verbindungen akzeptieren. Diese Konfiguration erfolgt in der `CreateWebHostBuilder`-Methode der `Program`-Klasse anstelle von `Startup`.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

Die Einstellung `ClientCertificateMode.RequireCertificate` bewirkt, dass Kestrel eine beliebige Verbindungsanforderung, die kein Client Zertifikat bereitstellt, sofort ablehnt, das Zertifikat jedoch nicht überprüft wird. Durch das Hinzufügen des `ClientCertificateValidation` Rückrufs ermöglicht Kestrel das Überprüfen des Client Zertifikats (in diesem Fall sicherzustellen, dass es von derselben *Zertifizierungs* Stelle wie das Serverzertifikat ausgestellt wurde) zu dem Zeitpunkt, an dem die Verbindung hergestellt wird, bevor die ASP.net Core Pipeline beteiligt ist.

### <a name="adding-aspnet-core-certificate-authentication"></a>Hinzufügen ASP.net Core Zertifikat Authentifizierung

Die Zertifikat Authentifizierung wird durch das nuget-Paket " [Microsoft. aspnetcore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) " bereitgestellt.

Fügen Sie den Zertifikat Authentifizierungsdienst in der `ConfigureServices`-Methode hinzu, und fügen Sie der ASP.net Core Pipeline in der `Configure`-Methode Authentifizierung und Autorisierung hinzu.

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="providing-channel-credentials-in-the-client-application"></a>Bereitstellen von Channel-Anmelde Informationen in der Client Anwendung

Mit dem `Grpc.Net.Client`-Paket werden Zertifikate auf einer <xref:System.Net.Http.HttpClient>-Instanz konfiguriert, die für den `GrpcChannel` bereitgestellt wird, der für die Verbindung verwendet wird.

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combining-channelcredentials-and-callcredentials"></a>Kombinieren von channelanmelde Informationen und callanmelde Informationen

Sie können den Server für die Verwendung der Zertifikat-und Tokenauthentifizierung konfigurieren, indem Sie die Zertifikat Änderungen auf den Kestrel-Server anwenden und die JWT-bearermiddleware in ASP.net Core verwenden.

Um channelanmelde Informationen und Call-Anmelde Informationen auf dem Client bereitzustellen, verwenden Sie die `ChannelCredentials.Create`-Methode, um die Aufruf Anmelde Informationen anzuwenden. Die Zertifikat Authentifizierung muss weiterhin mithilfe der <xref:System.Net.Http.HttpClient> Instanz angewendet werden: Wenn Sie Argumente an den `SslCredentials`-Konstruktor übergeben, löst der interne Client Code eine Ausnahme aus. Der `SslCredentials`-Parameter ist nur in der `Create`-Methode des `Grpc.Net.Client` Pakets enthalten, um die Kompatibilität mit dem `Grpc.Core` Paket aufrechtzuerhalten.

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> Sie können die `ChannelCredentials.Create`-Methode für einen Client ohne Zertifikat Authentifizierung verwenden, als nützliche Methode, um tokenanmelde Informationen mit jedem auf dem Kanal erfolgten Abruf zu übergeben.

Eine Version der [fullstockticker-Beispiel-GrpC-Anwendung mit hinzugefügter Zertifikat Authentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) finden Sie auf GitHub.

>[!div class="step-by-step"]
>[Zurück](call-credentials.md)
>[Weiter](encryption.md)
