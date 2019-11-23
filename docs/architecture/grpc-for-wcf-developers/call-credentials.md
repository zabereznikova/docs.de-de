---
title: Anmelde Informationen anrufen-GrpC für WCF-Entwickler
description: Vorgehensweise beim Implementieren und Verwenden von GrpC-Anmelde Informationen in ASP.net Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 2588fe3590a63ea6071b85ff29b3685efbfa25db
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968000"
---
# <a name="call-credentials"></a>Aufrufen von Anmeldeinformationen

Die Anmelde Informationen basieren alle auf einer Art von Token, die mit jeder Anforderung in Metadaten weitergegeben werden.

## <a name="ws-federation"></a>WS-Federation

ASP.net Core unterstützt den WS-Verbund mit dem [wsfederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) -nuget-Paket. WS-Federation ist die nächstgelegene Alternative zur Windows-Authentifizierung, die über http/2 nicht unterstützt wird. Benutzer werden mithilfe von Active Directory-Verbunddienste (AD FS) (ADFS) authentifiziert, das ein Token bereitstellt, das für die Authentifizierung bei ASP.net Core verwendet werden kann.

Weitere Informationen zu den ersten Schritten mit dieser Authentifizierungsmethode finden Sie [im Artikel Authentifizieren von Benutzern mit WS-Verbund in ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .

## <a name="jwt-bearer-tokens"></a>JWT-Träger Token

Der [JSON Web Token](https://jwt.io) Standard bietet eine Möglichkeit, Informationen über einen Benutzer und seine Ansprüche in einer codierten Zeichenfolge zu codieren und dieses Token so zu signieren, dass der Consumer die Integrität des Tokens mithilfe der Kryptografie mit öffentlichem Schlüssel überprüfen kann. Sie können verschiedene Dienste, wie z. b. IdentityServer4, zum Authentifizieren von Benutzern und Generieren von "oidc"-Token (OpenID Connect) für die Verwendung mit GrpC und http-APIs verwenden.

ASP.net Core 3,0 kann JSON-webtoken mithilfe des JWT-bearerpakets verarbeiten. Die Konfiguration ist für eine GrpC-Anwendung genauso wie eine ASP.net Core MVC-Anwendung.

In diesem Kapitel geht es um JWT-bearertoken, da diese einfacher mit dem WS-Verbund entwickelt werden können.

## <a name="adding-authentication-and-authorization-to-the-server"></a>Hinzufügen von Authentifizierung und Autorisierung zum Server

Das JWT-Träger Paket ist standardmäßig nicht in ASP.net Core 3,0 enthalten. Installieren Sie das nuget-Paket [Microsoft. aspnetcore. Authentication. jwtträger](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) in Ihrer APP.

Fügen Sie den Authentifizierungsdienst in der Startup-Klasse hinzu, und konfigurieren Sie den JWT-bearerhandler.

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

Die `IssuerSigningKey`-Eigenschaft erfordert eine Implementierung von `Microsoft.IdentityModels.Tokens.SecurityKey` mit den kryptografischen Daten, die zum Validieren der signierten Token erforderlich sind. Dieses Token sollte sicher in einem *Geheimnisse Server* wie Azure Key Vault gespeichert werden.

Fügen Sie als nächstes den Autorisierungs Dienst hinzu, der den Zugriff auf das System steuert.

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
> Authentifizierung und Autorisierung sind zwei separate Schritte. Die Authentifizierung wird verwendet, um die Identität des Benutzers zu bestimmen. Die Autorisierung entscheidet, ob dieser Benutzer auf verschiedene Teile des Systems zugreifen darf.

Fügen Sie nun die Authentifizierungs-und Autorisierungs Middleware der ASP.net Core Pipeline in der `Configure`-Methode hinzu.

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

Wenden Sie schließlich das `[Authorize]`-Attribut auf alle zu sichernden Dienste oder Methoden an, und verwenden Sie die `User`-Eigenschaft des zugrunde liegenden `HttpContext`, um die Berechtigungen zu überprüfen.

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

## <a name="providing-call-credentials-in-the-client-application"></a>Bereitstellen von Telefon Anmelde Informationen in der Client Anwendung

Nachdem Sie ein JWT-Token von einem Identitäts Server abgerufen haben, können Sie es zum Authentifizieren von GrpC-aufrufen vom Client verwenden, indem Sie es wie folgt als Metadatenheader für den Aufruf hinzufügen:

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

Nun haben Sie Ihren GrpC-Dienst mit JWT-bearertoken als Anmelde Informationen gesichert. Eine Version der [Beispiel-GrpC-Anwendung mit Authentifizierung und Autorisierung](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) finden Sie auf GitHub.

>[!div class="step-by-step"]
>[Zurück](security.md)
>[Weiter](channel-credentials.md)
