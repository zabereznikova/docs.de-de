---
title: Anmelde Informationen anrufen-GrpC für WCF-Entwickler
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-Anmelde Informationen in ASP.net Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f29d69ec37fe60bcd7ca01391001ea9eb71e7e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841672"
---
# <a name="call-credentials"></a><span data-ttu-id="0eaf5-103">Aufrufen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="0eaf5-103">Call credentials</span></span>

<span data-ttu-id="0eaf5-104">Die Anmelde Informationen basieren alle auf einer Art von Token, die mit jeder Anforderung in Metadaten weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-104">Call credentials are all based on some kind of token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="0eaf5-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="0eaf5-105">WS-Federation</span></span>

<span data-ttu-id="0eaf5-106">ASP.net Core unterstützt den WS-Verbund mit dem [wsfederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) -nuget-Paket.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="0eaf5-107">WS-Federation ist die nächstgelegene Alternative zur Windows-Authentifizierung, die über http/2 nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-107">WS-Federation is the closest available alternative to Windows Authentication, which is not supported over HTTP/2.</span></span> <span data-ttu-id="0eaf5-108">Benutzer werden mithilfe von Active Directory-Verbunddienste (AD FS) (ADFS) authentifiziert, das ein Token bereitstellt, das für die Authentifizierung bei ASP.net Core verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-108">Users are authenticated using Active Directory Federation Services (ADFS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="0eaf5-109">Weitere Informationen zu den ersten Schritten mit dieser Authentifizierungsmethode finden Sie [im Artikel Authentifizieren von Benutzern mit WS-Verbund in ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="0eaf5-109">For more information on how to get started with this authentication method, see the [Authenticate users with WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) article.</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="0eaf5-110">JWT-Träger Token</span><span class="sxs-lookup"><span data-stu-id="0eaf5-110">JWT Bearer tokens</span></span>

<span data-ttu-id="0eaf5-111">Der [JSON Web Token](https://jwt.io) Standard bietet eine Möglichkeit, Informationen über einen Benutzer und seine Ansprüche in einer codierten Zeichenfolge zu codieren und dieses Token so zu signieren, dass der Consumer die Integrität des Tokens mithilfe der Kryptografie mit öffentlichem Schlüssel überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-111">The [JSON Web Token](https://jwt.io) standard provides a way to encode information about a user and their claims in an encoded string, and to sign that token in such a way that the consumer can verify the integrity of the token using public key cryptography.</span></span> <span data-ttu-id="0eaf5-112">Sie können verschiedene Dienste, wie z. b. IdentityServer4, zum Authentifizieren von Benutzern und Generieren von "oidc"-Token (OpenID Connect) für die Verwendung mit GrpC und http-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-112">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="0eaf5-113">ASP.net Core 3,0 kann JSON-webtoken mithilfe des JWT-bearerpakets verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-113">ASP.NET Core 3.0 can handle JSON Web Tokens using the JWT Bearer package.</span></span> <span data-ttu-id="0eaf5-114">Die Konfiguration ist für eine GrpC-Anwendung genauso wie eine ASP.net Core MVC-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-114">The configuration is exactly the same for a gRPC application as an ASP.NET Core MVC application.</span></span>

<span data-ttu-id="0eaf5-115">In diesem Kapitel geht es um JWT-bearertoken, da diese einfacher mit dem WS-Verbund entwickelt werden können.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-115">This chapter will focus on JWT Bearer tokens as they're easier to develop with than WS-Federation.</span></span>

## <a name="adding-authentication-and-authorization-to-the-server"></a><span data-ttu-id="0eaf5-116">Hinzufügen von Authentifizierung und Autorisierung zum Server</span><span class="sxs-lookup"><span data-stu-id="0eaf5-116">Adding authentication and authorization to the server</span></span>

<span data-ttu-id="0eaf5-117">Das JWT-Träger Paket ist standardmäßig nicht in ASP.net Core 3,0 enthalten.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-117">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="0eaf5-118">Installieren Sie das nuget-Paket [Microsoft. aspnetcore. Authentication. jwtträger](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) in Ihrer APP.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-118">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="0eaf5-119">Fügen Sie den Authentifizierungsdienst in der Startup-Klasse hinzu, und konfigurieren Sie den JWT-bearerhandler.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-119">Add the Authentication service in the Startup class and configure the JWT Bearer handler.</span></span>

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

<span data-ttu-id="0eaf5-120">Die `IssuerSigningKey`-Eigenschaft erfordert eine Implementierung von `Microsoft.IdentityModels.Tokens.SecurityKey` mit den kryptografischen Daten, die zum Validieren der signierten Token erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-120">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="0eaf5-121">Dieses Token sollte sicher in einem *Geheimnisse Server* wie Azure Key Vault gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-121">This token should be stored securely in a *secrets server* like Azure KeyVault.</span></span>

<span data-ttu-id="0eaf5-122">Fügen Sie als nächstes den Autorisierungs Dienst hinzu, der den Zugriff auf das System steuert.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-122">Next add the Authorization service, which controls access to the system.</span></span>

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
> <span data-ttu-id="0eaf5-123">Authentifizierung und Autorisierung sind zwei separate Schritte.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-123">Authentication and Authorization are two separate steps.</span></span> <span data-ttu-id="0eaf5-124">Die Authentifizierung wird verwendet, um die Identität des Benutzers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-124">Authentication is used to determine the user's identity.</span></span> <span data-ttu-id="0eaf5-125">Die Autorisierung entscheidet, ob dieser Benutzer auf verschiedene Teile des Systems zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-125">Authorization decides whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="0eaf5-126">Fügen Sie nun die Authentifizierungs-und Autorisierungs Middleware der ASP.net Core Pipeline in der `Configure`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-126">Now add the Authentication and Authorization middleware to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

<span data-ttu-id="0eaf5-127">Wenden Sie schließlich das `[Authorize]`-Attribut auf alle zu sichernden Dienste oder Methoden an, und verwenden Sie die `User`-Eigenschaft des zugrunde liegenden `HttpContext`, um die Berechtigungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-127">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

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

## <a name="providing-call-credentials-in-the-client-application"></a><span data-ttu-id="0eaf5-128">Bereitstellen von Telefon Anmelde Informationen in der Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="0eaf5-128">Providing call credentials in the client application</span></span>

<span data-ttu-id="0eaf5-129">Nachdem Sie ein JWT-Token von einem Identitäts Server abgerufen haben, können Sie es zum Authentifizieren von GrpC-aufrufen vom Client verwenden, indem Sie es wie folgt als Metadatenheader für den Aufruf hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0eaf5-129">Once you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

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

<span data-ttu-id="0eaf5-130">Nun haben Sie Ihren GrpC-Dienst mit JWT-bearertoken als Anmelde Informationen gesichert.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-130">Now, you've secured your gRPC service using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="0eaf5-131">Eine Version der [Beispiel-GrpC-Anwendung mit Authentifizierung und Autorisierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="0eaf5-131">A version of the [Portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0eaf5-132">[Zurück](security.md)
>[Weiter](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="0eaf5-132">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
