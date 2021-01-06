---
title: 'Channel-Anmelde Informationen: GrpC für WCF-Entwickler'
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-channelanmelde Informationen in ASP.net Core 3,0.
ms.date: 12/15/2020
ms.openlocfilehash: 3663bbf061156db957241e2a32dbb9c64562ade2
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938636"
---
# <a name="channel-credentials"></a><span data-ttu-id="7ae64-103">Anmeldeinformationen für den Kanal</span><span class="sxs-lookup"><span data-stu-id="7ae64-103">Channel credentials</span></span>

<span data-ttu-id="7ae64-104">Wie der Name schon sagt, werden Channel-Anmelde Informationen an den zugrunde liegenden GrpC-Kanal angefügt.</span><span class="sxs-lookup"><span data-stu-id="7ae64-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="7ae64-105">Die Standardform der channelanmelde Informationen verwendet die Client Zertifikat Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7ae64-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="7ae64-106">Bei diesem Vorgang stellt der Client ein TLS-Zertifikat bereit, wenn die Verbindung hergestellt wird, und der Server überprüft dieses Zertifikat, bevor Aufrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7ae64-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this certificate before allowing any calls to be made.</span></span>

<span data-ttu-id="7ae64-107">Sie können channelanmelde Informationen mit Anmelde Informationen kombinieren, um eine umfassende Sicherheit für einen GrpC-Dienst bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7ae64-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="7ae64-108">Die channelanmeldungs-Anmelde Informationen belegen, dass die Client Anwendung auf den Dienst zugreifen darf, und die Anmelde Informationen enthalten Informationen über die Person, die die Client Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ae64-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="7ae64-109">Die Client Zertifikat Authentifizierung funktioniert für GrpC auf die gleiche Weise wie für ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="7ae64-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="7ae64-110">Weitere Informationen finden Sie unter [Konfigurieren der Zertifikat Authentifizierung in ASP.net Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="7ae64-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="7ae64-111">Für Entwicklungszwecke können Sie ein selbst signiertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7ae64-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="7ae64-112">Hinzufügen der Zertifikat Authentifizierung zum Server</span><span class="sxs-lookup"><span data-stu-id="7ae64-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="7ae64-113">Konfigurieren Sie die Zertifikat Authentifizierung auf Hostebene (z. b. auf dem Kestrel-Server) und in der ASP.net Core Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7ae64-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="7ae64-114">Konfigurieren der Zertifikat Überprüfung für Kestrel</span><span class="sxs-lookup"><span data-stu-id="7ae64-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="7ae64-115">Sie können Kestrel (den ASP.net Core http-Server) so konfigurieren, dass ein Client Zertifikat erforderlich ist. Optional können Sie eine Überprüfung des angegebenen Zertifikats ausführen, bevor Sie eingehende Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="7ae64-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="7ae64-116">Sie geben diese Konfiguration in der- `CreateWebHostBuilder` Methode der- `Program` Klasse anstelle von an `Startup` .</span><span class="sxs-lookup"><span data-stu-id="7ae64-116">You specify this configuration in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="7ae64-117">Die `ClientCertificateMode.RequireCertificate` Einstellung bewirkt, dass Kestrel eine beliebige Verbindungsanforderung, die kein Client Zertifikat bereitstellt, sofort ablehnt, aber diese Einstellung allein überprüft kein Zertifikat, das bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7ae64-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="7ae64-118">Fügen Sie den `ClientCertificateValidation` Rückruf hinzu, um Kestrel zum Überprüfen des Client Zertifikats an dem Punkt zu aktivieren, an dem die Verbindung hergestellt wird, bevor die ASP.net Core Pipeline beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="7ae64-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="7ae64-119">(In diesem Fall stellt der Rückruf sicher, dass er von derselben *Zertifizierungs* Stelle wie das Serverzertifikat ausgestellt wurde.)</span><span class="sxs-lookup"><span data-stu-id="7ae64-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="7ae64-120">Hinzufügen ASP.net Core Zertifikat Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7ae64-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="7ae64-121">Das nuget-Paket [Microsoft. aspnetcore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) bietet Zertifikat Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7ae64-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="7ae64-122">Fügen Sie den Zertifikat Authentifizierungsdienst in der `ConfigureServices` -Methode hinzu, und fügen Sie der ASP.net Core Pipeline in der-Methode Authentifizierung und Autorisierung hinzu `Configure` .</span><span class="sxs-lookup"><span data-stu-id="7ae64-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="7ae64-123">Angeben von Kanal Anmelde Informationen in der Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="7ae64-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="7ae64-124">Mit dem- `Grpc.Net.Client` Paket konfigurieren Sie Zertifikate für eine- <xref:System.Net.Http.HttpClient> Instanz, die für die bereitgestellt wird, die `GrpcChannel` für die Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ae64-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="7ae64-125">Kombinieren von channelanmelde Informationen und callanmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="7ae64-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="7ae64-126">Sie können den Server für die Verwendung der Zertifikat-und Tokenauthentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7ae64-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="7ae64-127">Wenden Sie hierzu die Zertifikat Änderungen auf den Kestrel-Server an, und verwenden Sie die JWT-bearermiddleware in ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="7ae64-127">To do this, apply the certificate changes to the Kestrel server, and use the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="7ae64-128">Um sowohl `ChannelCredentials` als auch `CallCredentials` auf dem Client bereitzustellen, verwenden Sie die- `ChannelCredentials.Create` Methode, um die Anmelde Informationen des Aufrufes</span><span class="sxs-lookup"><span data-stu-id="7ae64-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="7ae64-129">Sie müssen die Zertifikat Authentifizierung weiterhin mithilfe der- <xref:System.Net.Http.HttpClient> Instanz anwenden.</span><span class="sxs-lookup"><span data-stu-id="7ae64-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="7ae64-130">Wenn Sie Argumente an den `SslCredentials` Konstruktor übergeben, löst der interne Client Code eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="7ae64-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="7ae64-131">Der `SslCredentials` -Parameter ist nur in der `Grpc.Net.Client` -Methode des Pakets enthalten `Create` , um die Kompatibilität mit dem `Grpc.Core` Paket aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="7ae64-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="7ae64-132">Sie können die- `ChannelCredentials.Create` Methode für einen Client ohne Zertifikat Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ae64-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="7ae64-133">Dies ist eine nützliche Methode, um tokenanmelde Informationen mit jedem auf dem Kanal erfolgten Rückruf zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7ae64-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="7ae64-134">Eine Version der [fullstockticker-Beispiel-GrpC-Anwendung mit hinzugefügter Zertifikat Authentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="7ae64-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7ae64-135">[Zurück](call-credentials.md)
>[Weiter](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="7ae64-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
