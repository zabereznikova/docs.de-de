---
title: 'Channel-Anmelde Informationen: GrpC für WCF-Entwickler'
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-channelanmelde Informationen in ASP.net Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61141dc4143f36f9ac511c3369c3fde668c9d703
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841666"
---
# <a name="channel-credentials"></a><span data-ttu-id="62ec9-103">Anmeldeinformationen für den Kanal</span><span class="sxs-lookup"><span data-stu-id="62ec9-103">Channel credentials</span></span>

<span data-ttu-id="62ec9-104">Wie der Name schon sagt, werden Channel-Anmelde Informationen an den zugrunde liegenden GrpC-Kanal angefügt.</span><span class="sxs-lookup"><span data-stu-id="62ec9-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="62ec9-105">Die Standardform der channelanmelde Informationen verwendet die Client Zertifikat Authentifizierung, bei der der Client beim Herstellen der Verbindung ein TLS-Zertifikat bereitstellt, das vom Server überprüft wird, bevor Aufrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="62ec9-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="62ec9-106">Channelanmeldeinformationen können mit Anmelde Informationen kombiniert werden, um eine umfassende Sicherheit für einen GrpC-Dienst bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="62ec9-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="62ec9-107">Die channelanmeldeinformationen belegen, dass die Client Anwendung auf den Dienst zugreifen darf, und die Anmelde Informationen des Benutzers enthalten Informationen über die Person, die die Client Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="62ec9-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="62ec9-108">Die Client Zertifikat Authentifizierung funktioniert für GrpC auf die gleiche Weise wie für ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="62ec9-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="62ec9-109">Der Konfigurations Vorgang wird hier zusammengefasst, aber weitere Informationen finden Sie im Artikel [Konfigurieren der Zertifikat Authentifizierung in ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="62ec9-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="62ec9-110">Für Entwicklungszwecke können Sie ein selbst signiertes Zertifikat verwenden, aber für die Produktion sollten Sie ein ordnungsgemäßes HTTPS-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="62ec9-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="62ec9-111">Hinzufügen der Zertifikat Authentifizierung zum Server</span><span class="sxs-lookup"><span data-stu-id="62ec9-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="62ec9-112">Sie müssen die Zertifikat Authentifizierung auf Hostebene konfigurieren, z. b. auf dem Kestrel-Server und in der ASP.net Core Pipeline.</span><span class="sxs-lookup"><span data-stu-id="62ec9-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="62ec9-113">Konfigurieren der Zertifikat Überprüfung für Kestrel</span><span class="sxs-lookup"><span data-stu-id="62ec9-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="62ec9-114">Sie können Kestrel (den ASP.net Core http-Server) so konfigurieren, dass ein Client Zertifikat erforderlich ist. Optional können Sie auch eine Überprüfung des angegebenen Zertifikats ausführen, bevor Sie eingehende Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="62ec9-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="62ec9-115">Diese Konfiguration erfolgt in der `CreateWebHostBuilder`-Methode der `Program`-Klasse anstelle von `Startup`.</span><span class="sxs-lookup"><span data-stu-id="62ec9-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="62ec9-116">Die Einstellung `ClientCertificateMode.RequireCertificate` bewirkt, dass Kestrel eine beliebige Verbindungsanforderung, die kein Client Zertifikat bereitstellt, sofort ablehnt, das Zertifikat jedoch nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="62ec9-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="62ec9-117">Durch das Hinzufügen des `ClientCertificateValidation` Rückrufs ermöglicht Kestrel das Überprüfen des Client Zertifikats (in diesem Fall sicherzustellen, dass es von derselben *Zertifizierungs* Stelle wie das Serverzertifikat ausgestellt wurde) zu dem Zeitpunkt, an dem die Verbindung hergestellt wird, bevor die ASP.net Core Pipeline beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="62ec9-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="62ec9-118">Hinzufügen ASP.net Core Zertifikat Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="62ec9-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="62ec9-119">Die Zertifikat Authentifizierung wird durch das nuget-Paket " [Microsoft. aspnetcore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) " bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62ec9-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="62ec9-120">Fügen Sie den Zertifikat Authentifizierungsdienst in der `ConfigureServices`-Methode hinzu, und fügen Sie der ASP.net Core Pipeline in der `Configure`-Methode Authentifizierung und Autorisierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="62ec9-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="62ec9-121">Bereitstellen von Channel-Anmelde Informationen in der Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="62ec9-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="62ec9-122">Mit dem `Grpc.Net.Client`-Paket werden Zertifikate auf einer <xref:System.Net.Http.HttpClient>-Instanz konfiguriert, die für den `GrpcChannel` bereitgestellt wird, der für die Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62ec9-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="62ec9-123">Kombinieren von channelanmelde Informationen und callanmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="62ec9-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="62ec9-124">Sie können den Server für die Verwendung der Zertifikat-und Tokenauthentifizierung konfigurieren, indem Sie die Zertifikat Änderungen auf den Kestrel-Server anwenden und die JWT-bearermiddleware in ASP.net Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="62ec9-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="62ec9-125">Um channelanmelde Informationen und Call-Anmelde Informationen auf dem Client bereitzustellen, verwenden Sie die `ChannelCredentials.Create`-Methode, um die Aufruf Anmelde Informationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="62ec9-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="62ec9-126">Die Zertifikat Authentifizierung muss weiterhin mithilfe der <xref:System.Net.Http.HttpClient> Instanz angewendet werden: Wenn Sie Argumente an den `SslCredentials`-Konstruktor übergeben, löst der interne Client Code eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="62ec9-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="62ec9-127">Der `SslCredentials`-Parameter ist nur in der `Create`-Methode des `Grpc.Net.Client` Pakets enthalten, um die Kompatibilität mit dem `Grpc.Core` Paket aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="62ec9-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="62ec9-128">Sie können die `ChannelCredentials.Create`-Methode für einen Client ohne Zertifikat Authentifizierung verwenden, als nützliche Methode, um tokenanmelde Informationen mit jedem auf dem Kanal erfolgten Abruf zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="62ec9-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="62ec9-129">Eine Version der [fullstockticker-Beispiel-GrpC-Anwendung mit hinzugefügter Zertifikat Authentifizierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="62ec9-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="62ec9-130">[Zurück](call-credentials.md)
>[Weiter](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="62ec9-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
