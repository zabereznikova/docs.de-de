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
# <a name="channel-credentials"></a><span data-ttu-id="bd1f1-103">Anmeldeinformationen für den Kanal</span><span class="sxs-lookup"><span data-stu-id="bd1f1-103">Channel credentials</span></span>

<span data-ttu-id="bd1f1-104">Wie der Name schon sagt, werden Kanalanmeldeinformationen an den zugrunde liegenden gRPC-Kanal angefügt.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="bd1f1-105">Die Standardform der Kanalanmeldeinformationen verwendet die Clientzertifikatauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="bd1f1-106">In diesem Prozess stellt der Client ein TLS-Zertifikat bereit, wenn er die Verbindung herstellt, und dann überprüft der Server dies, bevor alle Aufrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="bd1f1-107">Sie können Kanalanmeldeinformationen mit Anrufanmeldeinformationen kombinieren, um umfassende Sicherheit für einen gRPC-Dienst zu bieten.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="bd1f1-108">Die Kanalanmeldeinformationen beweisen, dass die Clientanwendung auf den Dienst zugreifen darf, und die Anrufanmeldeinformationen enthalten Informationen über die Person, die die Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="bd1f1-109">Die Clientzertifikatauthentifizierung funktioniert für gRPC genauso wie für ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="bd1f1-110">Weitere Informationen finden Sie unter Konfigurieren der [Zertifikatauthentifizierung in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="bd1f1-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="bd1f1-111">Für Entwicklungszwecke können Sie ein selbstsigniertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Autorität signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="bd1f1-112">Hinzufügen der Zertifikatauthentifizierung zum Server</span><span class="sxs-lookup"><span data-stu-id="bd1f1-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="bd1f1-113">Konfigurieren Sie die Zertifikatauthentifizierung sowohl auf Hostebene (z. B. auf dem Kestrel-Server) als auch in der ASP.NET Core-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="bd1f1-114">Konfigurieren der Zertifikatvalidierung auf Kestrel</span><span class="sxs-lookup"><span data-stu-id="bd1f1-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="bd1f1-115">Sie können Kestrel (den ASP.NET Core-HTTP-Server) so konfigurieren, dass ein Clientzertifikat erforderlich ist, und optional eine Überprüfung des bereitgestellten Zertifikats durchführen, bevor Sie eingehende Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="bd1f1-116">Sie tun dies in der `CreateWebHostBuilder` Methode der `Program` Klasse und nicht in `Startup`.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="bd1f1-117">Die `ClientCertificateMode.RequireCertificate` Einstellung bewirkt, dass Kestrel jede Verbindungsanforderung, die kein Clientzertifikat bietet, sofort ablehnt, aber diese Einstellung selbst überprüft kein bereitgestelltes Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="bd1f1-118">Fügen `ClientCertificateValidation` Sie den Rückruf hinzu, damit Kestrel das Clientzertifikat an dem Punkt überprüfen kann, an dem die Verbindung hergestellt wird, bevor die ASP.NET Core-Pipeline aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="bd1f1-119">(In diesem Fall stellt der Rückruf sicher, dass er von derselben *Zertifizierungsstelle* wie das Serverzertifikat ausgestellt wurde.)</span><span class="sxs-lookup"><span data-stu-id="bd1f1-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="bd1f1-120">Hinzufügen ASP.NET Core-Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="bd1f1-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="bd1f1-121">Das NuGet-Paket [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) bietet zertifikatsauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="bd1f1-122">Fügen Sie den Zertifikatauthentifizierungsdienst in der `ConfigureServices` Methode hinzu, `Configure` und fügen Sie der ASP.NET Core-Pipeline in der Methode Authentifizierung und Autorisierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="bd1f1-123">Bereitstellen von Kanalanmeldeinformationen in der Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="bd1f1-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="bd1f1-124">Mit `Grpc.Net.Client` dem Paket konfigurieren Sie <xref:System.Net.Http.HttpClient> Zertifikate auf einer `GrpcChannel` Instanz, die für die für die Verbindung verwendete Instanz bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="bd1f1-125">Kombinieren von ChannelCredentials und CallCredentials</span><span class="sxs-lookup"><span data-stu-id="bd1f1-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="bd1f1-126">Sie können den Server so konfigurieren, dass er sowohl die Zertifikats- als auch die Tokenauthentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="bd1f1-127">Wenden Sie die Zertifikatsänderungen auf den Kestrel-Server an, und verwenden Sie die JWT-Träger-Middleware in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="bd1f1-128">Um sowohl `ChannelCredentials` `CallCredentials` auf dem Client `ChannelCredentials.Create` als auch auf dem Client bereitzustellen, verwenden Sie die Methode, um die Aufrufanmeldeinformationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="bd1f1-129">Sie müssen weiterhin die Zertifikatauthentifizierung mithilfe der <xref:System.Net.Http.HttpClient> Instanz anwenden.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="bd1f1-130">Wenn Sie Argumente an `SslCredentials` den Konstruktor übergeben, löst der interne Clientcode eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="bd1f1-131">Der `SslCredentials` Parameter ist nur `Grpc.Net.Client` in `Create` der Methode des Pakets `Grpc.Core` enthalten, um die Kompatibilität mit dem Paket aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="bd1f1-132">Sie können `ChannelCredentials.Create` die Methode für einen Client ohne Zertifikatauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="bd1f1-133">Dies ist eine nützliche Möglichkeit, Tokenanmeldeinformationen mit jedem Aufruf auf dem Kanal zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="bd1f1-134">Eine Version der [FullStockTicker-Beispiel-gRPC-Anwendung mit hinzugefügter Zertifikatauthentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) befindet sich auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bd1f1-135">[VorherigeS](call-credentials.md)
>[Weiter](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="bd1f1-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
