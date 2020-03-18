---
title: Channel-Anmeldeinformationen - gRPC für WCF-Entwickler
description: Implementieren und verwenden sie gRPC-Kanalanmeldeinformationen in ASP.NET Core 3.0.
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148204"
---
# <a name="channel-credentials"></a>Anmeldeinformationen für den Kanal

Wie der Name schon sagt, werden Kanalanmeldeinformationen an den zugrunde liegenden gRPC-Kanal angefügt. Die Standardform der Kanalanmeldeinformationen verwendet die Clientzertifikatauthentifizierung. In diesem Prozess stellt der Client ein TLS-Zertifikat bereit, wenn er die Verbindung herstellt, und dann überprüft der Server dies, bevor alle Aufrufe zugelassen werden.

Sie können Kanalanmeldeinformationen mit Anrufanmeldeinformationen kombinieren, um umfassende Sicherheit für einen gRPC-Dienst zu bieten. Die Kanalanmeldeinformationen beweisen, dass die Clientanwendung auf den Dienst zugreifen darf, und die Anrufanmeldeinformationen enthalten Informationen über die Person, die die Clientanwendung verwendet.

Die Clientzertifikatauthentifizierung funktioniert für gRPC genauso wie für ASP.NET Core. Weitere Informationen finden Sie unter Konfigurieren der [Zertifikatauthentifizierung in ASP.NET Core](/aspnet/core/security/authentication/certauth).

Für Entwicklungszwecke können Sie ein selbstsigniertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Autorität signiert wurde.

## <a name="add-certificate-authentication-to-the-server"></a>Hinzufügen der Zertifikatauthentifizierung zum Server

Konfigurieren Sie die Zertifikatauthentifizierung sowohl auf Hostebene (z. B. auf dem Kestrel-Server) als auch in der ASP.NET Core-Pipeline.

### <a name="configure-certificate-validation-on-kestrel"></a>Konfigurieren der Zertifikatvalidierung auf Kestrel

Sie können Kestrel (den ASP.NET Core-HTTP-Server) so konfigurieren, dass ein Clientzertifikat erforderlich ist, und optional eine Überprüfung des bereitgestellten Zertifikats durchführen, bevor Sie eingehende Verbindungen akzeptieren. Sie tun dies in der `CreateWebHostBuilder` Methode der `Program` Klasse und nicht in `Startup`.

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

Die `ClientCertificateMode.RequireCertificate` Einstellung bewirkt, dass Kestrel jede Verbindungsanforderung, die kein Clientzertifikat bietet, sofort ablehnt, aber diese Einstellung selbst überprüft kein bereitgestelltes Zertifikat. Fügen `ClientCertificateValidation` Sie den Rückruf hinzu, damit Kestrel das Clientzertifikat an dem Punkt überprüfen kann, an dem die Verbindung hergestellt wird, bevor die ASP.NET Core-Pipeline aktiviert wird. (In diesem Fall stellt der Rückruf sicher, dass er von derselben *Zertifizierungsstelle* wie das Serverzertifikat ausgestellt wurde.)

### <a name="add-aspnet-core-certificate-authentication"></a>Hinzufügen ASP.NET Core-Zertifikatauthentifizierung

Das NuGet-Paket [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) bietet zertifikatsauthentifizierung.

Fügen Sie den Zertifikatauthentifizierungsdienst in der `ConfigureServices` Methode hinzu, `Configure` und fügen Sie der ASP.NET Core-Pipeline in der Methode Authentifizierung und Autorisierung hinzu.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Bereitstellen von Kanalanmeldeinformationen in der Clientanwendung

Mit `Grpc.Net.Client` dem Paket konfigurieren Sie <xref:System.Net.Http.HttpClient> Zertifikate auf einer `GrpcChannel` Instanz, die für die für die Verbindung verwendete Instanz bereitgestellt wird.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Kombinieren von ChannelCredentials und CallCredentials

Sie können den Server so konfigurieren, dass er sowohl die Zertifikats- als auch die Tokenauthentifizierung verwendet. Wenden Sie die Zertifikatsänderungen auf den Kestrel-Server an, und verwenden Sie die JWT-Träger-Middleware in ASP.NET Core.

Um sowohl `ChannelCredentials` `CallCredentials` auf dem Client `ChannelCredentials.Create` als auch auf dem Client bereitzustellen, verwenden Sie die Methode, um die Aufrufanmeldeinformationen anzuwenden. Sie müssen weiterhin die Zertifikatauthentifizierung mithilfe der <xref:System.Net.Http.HttpClient> Instanz anwenden. Wenn Sie Argumente an `SslCredentials` den Konstruktor übergeben, löst der interne Clientcode eine Ausnahme aus. Der `SslCredentials` Parameter ist nur `Grpc.Net.Client` in `Create` der Methode des Pakets `Grpc.Core` enthalten, um die Kompatibilität mit dem Paket aufrechtzuerhalten.

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
> Sie können `ChannelCredentials.Create` die Methode für einen Client ohne Zertifikatauthentifizierung verwenden. Dies ist eine nützliche Möglichkeit, Tokenanmeldeinformationen mit jedem Aufruf auf dem Kanal zu übergeben.

Eine Version der [FullStockTicker-Beispiel-gRPC-Anwendung mit hinzugefügter Zertifikatauthentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) befindet sich auf GitHub.

>[!div class="step-by-step"]
>[VorherigeS](call-credentials.md)
>[Weiter](encryption.md)
