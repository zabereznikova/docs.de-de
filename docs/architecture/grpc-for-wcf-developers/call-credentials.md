---
title: Anmelde Informationen anrufen-GrpC für WCF-Entwickler
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-Anmelde Informationen in ASP.net Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 01f21f58ed4235f45509c948c84653cd99d35618
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711537"
---
# <a name="call-credentials"></a><span data-ttu-id="c0c92-103">Aufrufen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="c0c92-103">Call credentials</span></span>

<span data-ttu-id="c0c92-104">Die Anmelde Informationen basieren alle auf einem Token, das mit jeder Anforderung in Metadaten weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c0c92-104">Call credentials are all based on a token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="c0c92-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="c0c92-105">WS-Federation</span></span>

<span data-ttu-id="c0c92-106">ASP.net Core unterstützt den WS-Verbund mit dem [wsfederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) -nuget-Paket.</span><span class="sxs-lookup"><span data-stu-id="c0c92-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="c0c92-107">WS-Federation ist die nächstgelegene Alternative zur Windows-Authentifizierung, die über http/2 nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c0c92-107">WS-Federation is the closest available alternative to Windows Authentication, which isn't supported over HTTP/2.</span></span> <span data-ttu-id="c0c92-108">Benutzer werden mithilfe Active Directory-Verbunddienste (AD FS) (AD FS) authentifiziert, das ein Token bereitstellt, das für die Authentifizierung mit ASP.net Core verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0c92-108">Users are authenticated by using Active Directory Federation Services (AD FS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="c0c92-109">Weitere Informationen zu den ersten Schritten mit dieser Authentifizierungsmethode finden Sie unter [Authentifizieren von Benutzern mit dem WS-Verbund in ASP.net Core](/aspnet/core/security/authentication/ws-federation).</span><span class="sxs-lookup"><span data-stu-id="c0c92-109">For more information on how to get started with this authentication method, see [Authenticate users with WS-Federation in ASP.NET Core](/aspnet/core/security/authentication/ws-federation).</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="c0c92-110">JWT-Träger Token</span><span class="sxs-lookup"><span data-stu-id="c0c92-110">JWT Bearer tokens</span></span>

<span data-ttu-id="c0c92-111">Der [JSON Web Token](https://jwt.io) (JWT)-Standard bietet eine Möglichkeit, Informationen über einen Benutzer und seine Ansprüche in einer codierten Zeichenfolge zu codieren.</span><span class="sxs-lookup"><span data-stu-id="c0c92-111">The [JSON Web Token](https://jwt.io) (JWT) standard provides a way to encode information about a user and their claims in an encoded string.</span></span> <span data-ttu-id="c0c92-112">Außerdem bietet es eine Möglichkeit, das Token zu signieren, damit der Consumer die Integrität des Tokens mithilfe der Kryptografie mit öffentlichem Schlüssel überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="c0c92-112">It also provides a way to sign that token, so that the consumer can verify the integrity of the token by using public key cryptography.</span></span> <span data-ttu-id="c0c92-113">Sie können verschiedene Dienste, wie z. b. IdentityServer4, zum Authentifizieren von Benutzern und Generieren von "oidc"-Token (OpenID Connect) für die Verwendung mit GrpC und http-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0c92-113">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="c0c92-114">ASP.net Core 3,0 kann jwts mithilfe des JWT-bearerpakets verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c0c92-114">ASP.NET Core 3.0 can handle JWTs by using the JWT Bearer package.</span></span> <span data-ttu-id="c0c92-115">Die Konfiguration ist für eine GrpC-Anwendung genauso wie für eine ASP.net Core MVC-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c0c92-115">The configuration is exactly the same for a gRPC application as it is for an ASP.NET Core MVC application.</span></span> <span data-ttu-id="c0c92-116">Hier konzentrieren wir uns auf JWT-bearertoken, da Sie einfacher mit als WS-Federation entwickelt werden können.</span><span class="sxs-lookup"><span data-stu-id="c0c92-116">Here, we'll focus on JWT Bearer tokens, because they're easier to develop with than WS-Federation.</span></span>

## <a name="add-authentication-and-authorization-to-the-server"></a><span data-ttu-id="c0c92-117">Hinzufügen von Authentifizierung und Autorisierung zum Server</span><span class="sxs-lookup"><span data-stu-id="c0c92-117">Add authentication and authorization to the server</span></span>

<span data-ttu-id="c0c92-118">Das JWT-Träger Paket ist standardmäßig nicht in ASP.net Core 3,0 enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0c92-118">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="c0c92-119">Installieren Sie das nuget-Paket [Microsoft. aspnetcore. Authentication. jwtträger](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) in Ihrer APP.</span><span class="sxs-lookup"><span data-stu-id="c0c92-119">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="c0c92-120">Fügen Sie den Authentifizierungsdienst in der Startup-Klasse hinzu, und konfigurieren Sie den JWT-bearerhandler:</span><span class="sxs-lookup"><span data-stu-id="c0c92-120">Add the Authentication service in the Startup class, and configure the JWT Bearer handler:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

<span data-ttu-id="c0c92-121">Die `IssuerSigningKey`-Eigenschaft erfordert eine Implementierung von `Microsoft.IdentityModels.Tokens.SecurityKey` mit den kryptografischen Daten, die zum Validieren der signierten Token erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c0c92-121">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="c0c92-122">Speichern Sie dieses Token sicher in einem *Geheimnisse Server*, wie Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c0c92-122">Store this token securely in a *secrets server*, like Azure Key Vault.</span></span>

<span data-ttu-id="c0c92-123">Fügen Sie als nächstes den Autorisierungs Dienst hinzu, der den Zugriff auf das System steuert:</span><span class="sxs-lookup"><span data-stu-id="c0c92-123">Next, add the Authorization service, which controls access to the system:</span></span>

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> <span data-ttu-id="c0c92-124">Authentifizierung und Autorisierung sind zwei separate Schritte.</span><span class="sxs-lookup"><span data-stu-id="c0c92-124">Authentication and authorization are two separate steps.</span></span> <span data-ttu-id="c0c92-125">Sie verwenden die-Authentifizierung, um die Identität des Benutzers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c0c92-125">You use authentication to determine the user's identity.</span></span> <span data-ttu-id="c0c92-126">Mithilfe der Autorisierung können Sie entscheiden, ob dieser Benutzer auf verschiedene Teile des Systems zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="c0c92-126">You use authorization to decide whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="c0c92-127">Fügen Sie nun die Authentifizierungs-und Autorisierungs Middleware der ASP.net Core Pipeline in der `Configure`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="c0c92-127">Now add the authentication and authorization middleware to the ASP.NET Core pipeline in the `Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="c0c92-128">Wenden Sie schließlich das `[Authorize]`-Attribut auf alle zu sichernden Dienste oder Methoden an, und verwenden Sie die `User`-Eigenschaft des zugrunde liegenden `HttpContext`, um die Berechtigungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c0c92-128">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="provide-call-credentials-in-the-client-application"></a><span data-ttu-id="c0c92-129">Angeben von Telefon Anmelde Informationen in der Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="c0c92-129">Provide call credentials in the client application</span></span>

<span data-ttu-id="c0c92-130">Nachdem Sie ein JWT-Token von einem Identitäts Server abgerufen haben, können Sie es zum Authentifizieren von GrpC-aufrufen vom Client verwenden, indem Sie es wie folgt als Metadatenheader für den Aufruf hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c0c92-130">After you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

<span data-ttu-id="c0c92-131">Nun haben Sie Ihren GrpC-Dienst mit JWT-bearertoken als Anmelde Informationen gesichert.</span><span class="sxs-lookup"><span data-stu-id="c0c92-131">Now you've secured your gRPC service by using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="c0c92-132">Eine Version der [Beispiel-GrpC-Anwendung mit Authentifizierung und Autorisierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="c0c92-132">A version of the [portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c0c92-133">[Zurück](security.md)
>[Weiter](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="c0c92-133">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
