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
# <a name="call-credentials"></a>Aufrufen von Anmeldeinformationen

Die Anmelde Informationen basieren alle auf einem Token, das mit jeder Anforderung in Metadaten weitergegeben wurde.

## <a name="ws-federation"></a>WS-Federation

ASP.net Core unterstützt den WS-Verbund mit dem [wsfederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) -nuget-Paket. WS-Federation ist die nächstgelegene Alternative zur Windows-Authentifizierung, die über http/2 nicht unterstützt wird. Benutzer werden mithilfe Active Directory-Verbunddienste (AD FS) (AD FS) authentifiziert, das ein Token bereitstellt, das für die Authentifizierung mit ASP.net Core verwendet werden kann.

Weitere Informationen zu den ersten Schritten mit dieser Authentifizierungsmethode finden Sie unter [Authentifizieren von Benutzern mit dem WS-Verbund in ASP.net Core](/aspnet/core/security/authentication/ws-federation).

## <a name="jwt-bearer-tokens"></a>JWT-Träger Token

Der [JSON Web Token](https://jwt.io) (JWT)-Standard bietet eine Möglichkeit, Informationen über einen Benutzer und seine Ansprüche in einer codierten Zeichenfolge zu codieren. Außerdem bietet es eine Möglichkeit, das Token zu signieren, damit der Consumer die Integrität des Tokens mithilfe der Kryptografie mit öffentlichem Schlüssel überprüfen kann. Sie können verschiedene Dienste, wie z. b. IdentityServer4, zum Authentifizieren von Benutzern und Generieren von "oidc"-Token (OpenID Connect) für die Verwendung mit GrpC und http-APIs verwenden.

ASP.net Core 3,0 kann jwts mithilfe des JWT-bearerpakets verarbeiten. Die Konfiguration ist für eine GrpC-Anwendung genauso wie für eine ASP.net Core MVC-Anwendung. Hier konzentrieren wir uns auf JWT-bearertoken, da Sie einfacher mit als WS-Federation entwickelt werden können.

## <a name="add-authentication-and-authorization-to-the-server"></a>Hinzufügen von Authentifizierung und Autorisierung zum Server

Das JWT-Träger Paket ist standardmäßig nicht in ASP.net Core 3,0 enthalten. Installieren Sie das nuget-Paket [Microsoft. aspnetcore. Authentication. jwtträger](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) in Ihrer APP.

Fügen Sie den Authentifizierungsdienst in der Startup-Klasse hinzu, und konfigurieren Sie den JWT-bearerhandler:

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

Die `IssuerSigningKey`-Eigenschaft erfordert eine Implementierung von `Microsoft.IdentityModels.Tokens.SecurityKey` mit den kryptografischen Daten, die zum Validieren der signierten Token erforderlich sind. Speichern Sie dieses Token sicher in einem *Geheimnisse Server*, wie Azure Key Vault.

Fügen Sie als nächstes den Autorisierungs Dienst hinzu, der den Zugriff auf das System steuert:

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
> Authentifizierung und Autorisierung sind zwei separate Schritte. Sie verwenden die-Authentifizierung, um die Identität des Benutzers zu bestimmen. Mithilfe der Autorisierung können Sie entscheiden, ob dieser Benutzer auf verschiedene Teile des Systems zugreifen darf.

Fügen Sie nun die Authentifizierungs-und Autorisierungs Middleware der ASP.net Core Pipeline in der `Configure`-Methode hinzu:

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

## <a name="provide-call-credentials-in-the-client-application"></a>Angeben von Telefon Anmelde Informationen in der Client Anwendung

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
