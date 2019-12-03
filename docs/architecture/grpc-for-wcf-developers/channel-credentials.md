---
title: 'Channel-Anmelde Informationen: GrpC für WCF-Entwickler'
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-channelanmelde Informationen in ASP.net Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711490"
---
# <a name="channel-credentials"></a>Anmeldeinformationen für den Kanal

Wie der Name schon sagt, werden Channel-Anmelde Informationen an den zugrunde liegenden GrpC-Kanal angefügt. Die Standardform der channelanmelde Informationen verwendet die Client Zertifikat Authentifizierung. Bei diesem Vorgang stellt der Client ein TLS-Zertifikat bereit, wenn die Verbindung hergestellt wird, und der Server überprüft dies, bevor Aufrufe zugelassen werden.

Sie können channelanmelde Informationen mit Anmelde Informationen kombinieren, um eine umfassende Sicherheit für einen GrpC-Dienst bereitzustellen. Die channelanmeldungs-Anmelde Informationen belegen, dass die Client Anwendung auf den Dienst zugreifen darf, und die Anmelde Informationen enthalten Informationen über die Person, die die Client Anwendung verwendet.

Die Client Zertifikat Authentifizierung funktioniert für GrpC auf die gleiche Weise wie für ASP.net Core. Weitere Informationen finden Sie unter [Konfigurieren der Zertifikat Authentifizierung in ASP.net Core](/aspnet/core/security/authentication/certauth).

Für Entwicklungszwecke können Sie ein selbst signiertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle signiert wurde.

## <a name="add-certificate-authentication-to-the-server"></a>Hinzufügen der Zertifikat Authentifizierung zum Server

Konfigurieren Sie die Zertifikat Authentifizierung auf Hostebene (z. b. auf dem Kestrel-Server) und in der ASP.net Core Pipeline.

### <a name="configure-certificate-validation-on-kestrel"></a>Konfigurieren der Zertifikat Überprüfung für Kestrel

Sie können Kestrel (den ASP.net Core http-Server) so konfigurieren, dass ein Client Zertifikat erforderlich ist. Optional können Sie eine Überprüfung des angegebenen Zertifikats ausführen, bevor Sie eingehende Verbindungen akzeptieren. Dies wird in der `CreateWebHostBuilder`-Methode der `Program`-Klasse und nicht in `Startup`durchführen.

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

Die Einstellung `ClientCertificateMode.RequireCertificate` bewirkt, dass Kestrel jede Verbindungsanforderung, die kein Client Zertifikat bereitstellt, sofort ablehnt, aber diese Einstellung allein überprüft kein Zertifikat, das bereitgestellt wird. Fügen Sie den `ClientCertificateValidation` Rückruf hinzu, damit Kestrel das Client Zertifikat an dem Punkt, an dem die Verbindung hergestellt wird, überprüfen kann, bevor die ASP.net Core Pipeline beteiligt ist. (In diesem Fall stellt der Rückruf sicher, dass er von derselben *Zertifizierungs* Stelle wie das Serverzertifikat ausgestellt wurde.) 

### <a name="add-aspnet-core-certificate-authentication"></a>Hinzufügen ASP.net Core Zertifikat Authentifizierung

Das nuget-Paket [Microsoft. aspnetcore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) bietet Zertifikat Authentifizierung.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Angeben von Kanal Anmelde Informationen in der Client Anwendung

Mit dem `Grpc.Net.Client`-Paket konfigurieren Sie Zertifikate auf einer <xref:System.Net.Http.HttpClient>-Instanz, die für den `GrpcChannel` bereitgestellt wird, der für die Verbindung verwendet wird.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Kombinieren von channelanmelde Informationen und callanmelde Informationen

Sie können den Server für die Verwendung der Zertifikat-und Tokenauthentifizierung konfigurieren. Hierzu wenden Sie die Zertifikat Änderungen auf den Kestrel-Server an und verwenden die JWT-bearermiddleware in ASP.net Core.

Um `ChannelCredentials` und `CallCredentials` auf dem Client bereitzustellen, verwenden Sie die `ChannelCredentials.Create`-Methode, um die Anmelde Informationen für den-Befehl anzuwenden. Sie müssen die Zertifikat Authentifizierung weiterhin mithilfe der <xref:System.Net.Http.HttpClient> Instanz anwenden. Wenn Sie Argumente an den `SslCredentials`-Konstruktor übergeben, löst der interne Client Code eine Ausnahme aus. Der `SslCredentials`-Parameter ist nur in der `Create`-Methode des `Grpc.Net.Client` Pakets enthalten, um die Kompatibilität mit dem `Grpc.Core` Paket aufrechtzuerhalten.

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
> Sie können die `ChannelCredentials.Create`-Methode für einen Client ohne Zertifikat Authentifizierung verwenden. Dies ist eine nützliche Methode, um tokenanmelde Informationen mit jedem auf dem Kanal erfolgten Rückruf zu übergeben.

Eine Version der [fullstockticker-Beispiel-GrpC-Anwendung mit hinzugefügter Zertifikat Authentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) finden Sie auf GitHub.

>[!div class="step-by-step"]
>[Zurück](call-credentials.md)
>[Weiter](encryption.md)
