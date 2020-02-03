---
title: Sichern von .NET-Microservices und Webanwendungen
description: Sicherheit in .NET-Microservices und -Webanwendungen – Lernen Sie die Authentifizierungsoptionen in ASP.NET Core-Webanwendungen kennen.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 6d318f4efc6958610947f164d6ca63634f3d7db5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777213"
---
# <a name="make-secure-net-microservices-and-web-applications"></a>Erstellen sicherer .NET-Microservices und -Webanwendungen

Das Thema Sicherheit in Microservices und Webanwendungen hat so viele Aspekte, dass zu seiner Behandlung gleich mehrere Bücher wie dieses erforderlich wären – daher wollen wir uns in diesem Abschnitt auf Authentifizierung, Autorisierung und Anwendungsgeheimnisse konzentrieren.

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a>Implementieren von Authentifizierung in .NET-Microservices und -Webanwendungen

Ressourcen und APIs, die durch einen Dienst veröffentlicht wurden, müssen oftmals auf bestimmte vertrauenswürdige Benutzer oder Clients beschränkt werden. Der erste Schritt zur Durchführung dieser Entscheidungen über die Vertrauenswürdigkeit auf API-Ebene ist die Authentifizierung. Authentifizierung bezeichnet den Vorgang der zuverlässigen Überprüfung der Identität eines Benutzers.

In Microservice-Szenarios wird die Authentifizierung in der Regel zentral verarbeitet. Wenn Sie ein API-Gateway verwenden, ist dieses Gateway ein guter Ort, um die Authentifizierung durchzuführen, so wie in Abbildung 9-1 dargestellt. Wenn Sie nach diesem Ansatz vorgehen, stellen Sie sicher, dass die einzelnen Microservices nicht direkt (ohne das API-Gateway) erreicht werden können, außer es kann zusätzliche Sicherheit garantiert werden, um Benachrichtigen danach zu authentifizieren, ob sie vom Gateway stammen oder nicht.

![Das folgenden Diagramm zeigt, wie die mobile Client-App mit dem Back-End interagiert.](./media/index/api-gateway-centralized-authentication.png)

**Abbildung 9-1**. Zentrale Authentifizierung mit einem API-Gateway

Wenn die Authentifizierung im API-Gateway zentralisiert ist, fügt dieses Anforderungen beim Weiterleiten an die Microservices Benutzerinformationen hinzu. Wenn auf Dienste direkt zugegriffen werden kann, kann ein Authentifizierungsdienst wie Azure Active Directory oder ein dedizierter Authentifizierungs-Microservice, der als Sicherheitstokendienst (STS) fungiert, zum Authentifizieren von Benutzern verwendet werden. Entscheidungen über die Vertrauenswürdigkeit werden zwischen Diensten mit Sicherheitstoken oder Cookies freigegeben. (Diese Token können bei Bedarf zwischen ASP.NET Core-Anwendungen durch Implementierung der [gemeinsamen Nutzung von Cookies](/aspnet/core/security/cookie-sharing) freigegeben werden.) Dieses Muster ist in Abbildung 9-2 dargestellt.

![Das folgende Diagramm zeigt die Authentifizierung durch Back-End-Microservices.](./media/index/identity-microservice-authentication.png)

**Abbildung 9-2:** Authentifizierung durch Identitäts-Microservice; das Vertrauen ist mithilfe eines Autorisierungstokens freigegeben.

Beim direkten Zugriff auf Microservices wird die Vertrauensstellung, die Authentifizierung und Autorisierung beinhaltet, mithilfe eines Sicherheitstokens behandelt, das von einem von den Microservices gemeinsam verwendeten, dedizierten Microservice herausgegeben wird.

### <a name="authenticate-with-aspnet-core-identity"></a>Authentifizierung mit ASP.NET Core Identity

Der primäre Mechanismus in ASP.NET Core zur Identifizierung eines Anwendungsbenutzers ist das Mitgliedschaftssystem [ASP.NET Core Identity](/aspnet/core/security/authentication/identity). ASP.NET Core Identity speichert Benutzerinformationen (einschließlich Anmeldeinformationen, Rollen und Ansprüche) in einem Datenspeicher, der vom Entwickler konfiguriert wurde. Normalerweise ist der ASP.NET Core Identity-Datenspeicher ein Entity Framework-Speicher, der im `Microsoft.AspNetCore.Identity.EntityFrameworkCore`-Paket bereitgestellt wird. Jedoch können benutzerdefinierte Speicher oder andere Pakete von Drittanbietern zum Speichern von Identitätsinformationen in Azure Table Storage, CosmosDB oder anderen Speicherorten verwendet werden.

Der folgende Code wird aus der Projektvorlage der ASP.NET Core-Webanwendung genommen, für die eine einzelne Benutzerkontoauthentifizierung ausgewählt ist. Er stellt dar, wie ASP.NET Core Identiy mithilfe von EntityFramework.Core in der Startup.ConfigureServices-Methode konfiguriert wird.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

Sobald ASP.NET Core Identity konfiguriert ist, aktivieren Sie den Dienst, indem Sie „app.UseIdentity“ in der `Startup.Configure`-Methode des Diensts aufrufen.

Durch die Verwendung von ASP.NET Core Identity sind mehrere Szenarios möglich:

- Erstellen Sie neue Benutzerinformationen mithilfe des UserManager-Typs (userManager.CreateAsync).

- Authentifizieren Sie Benutzer mithilfe des SignInManager-Typs. Sie können `signInManager.SignInAsync` für die direkte Anmeldung verwenden oder mithilfe von `signInManager.PasswordSignInAsync` die Richtigkeit des Benutzerkennworts bestätigen und diesen anschließend anmelden.

- Identifizieren Sie einen Benutzer auf Grundlage von Informationen, die in einem Cookie gespeichert sind (das von der ASP.NET Core Identity-Middleware gelesen wird), damit nachfolgende Anforderungen von einem Browser die Identität und Ansprüche eines angemeldeten Benutzers enthalten.

ASP.NET Core Identity unterstützt auch die [zweistufige Authentifizierung](/aspnet/core/security/authentication/2fa).

ASP.NET Core Identity ist eine empfohlene Lösung für Authentifizierungsszenarios, die einen Datenspeicher für lokale Benutzerdaten verwenden und die Identität zwischen Anforderungen mithilfe von Cookies (was typisch für MVC-Webanwendungen ist) beibehalten.

### <a name="authenticate-with-external-providers"></a>Authentifizierung mithilfe externer Anbieter

ASP.NET Core unterstützt auch die Verwendung von [externen Authentifizierungsanbietern](/aspnet/core/security/authentication/social/), damit sich Benutzer über [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)-Flows anmelden können. Das bedeutet, dass sich Benutzer mithilfe von vorhandenen Authentifizierungsprozessen von Anbietern wie Microsoft, Google, Facebook oder Twitter anmelden können und diese Identitäten ASP.NET Core Identity in Ihrer Anwendung zuordnen können.

Für die Verwendung der externen Authentifizierung schließen Sie die entsprechende Authentifizierungsmiddleware in der HTTP-Pipeline zum Verarbeiten von Anforderungen ein. Diese Middleware ist für die Verarbeitung von Anforderungen verantwortlich, um URI-Routen vom Authentifizierungsanbieter zurückzugeben, um Identitätsinformationen zu erfassen und diese über die SignInManager.GetExternalLoginInfo-Methode verfügbar zu machen.

Beliebte externe Authentifizierungsanbieter sowie deren zugeordnete NuGet-Pakete sind in der folgenden Tabelle dargestellt:

| **Anbieter**  | **Pakete**                                          |
| ------------- | ---------------------------------------------------- |
| **Microsoft** | **Microsoft.AspNetCore.Authentication.MicrosoftAccount** |
| **Google**    | **Microsoft.AspNetCore.Authentication.Google**           |
| **Facebook**  | **Microsoft.AspNetCore.Authentication.Facebook**         |
| **Twitter**   | **Microsoft.AspNetCore.Authentication.Twitter**          |

In allen Fällen wird die Middleware mithilfe eines Aufrufs einer Registrierungsmethode registriert, ähnlich wie `app.Use{ExternalProvider}Authentication` in `Startup.Configure`. Diese Registrierungsmethoden nehmen ein Options-Objekt, das je nach Anbieter eine Anwendungs-ID sowie geheime Informationen (beispielsweise ein Kennwort) enthält. Externe Authentifizierungsanbieter erfordern, dass die Anwendung registriert ist (so wie in der [ASP.NET Core-Dokumentation beschrieben](/aspnet/core/security/authentication/social/)), sodass sie den Benutzer darüber informieren können, welche Anwendung Zugriff auf ihre Identität anfordert.

Sobald die Middleware in `Startup.Configure` registriert ist, können Sie Benutzer auffordern, sich von einer beliebigen Controlleraktion aus anzumelden. Um dies zu ermöglichen, erstellen Sie ein `AuthenticationProperties`-Objekt, das den Namen und die Umleitungs-URL des Authentifizierungsanbieters enthält. Sie geben anschließend eine „Challenge“-Antwort zurück, die das `AuthenticationProperties`-Objekt übergibt. Im folgenden Code ist ein Beispiel dafür dargestellt.

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

Der redirectUrl-Parameter enthält die URL, auf die der externe Anbieter umleiten soll, sobald sich der Benutzer authentifiziert hat. Die URL sollte eine Aktion darstellen, die den Benutzer, wie im folgenden vereinfachten Beispiel dargestellt, auf Grundlage externer Identitätsinformationen anmelden soll:

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

Wenn Sie die Authentifizierungsoption **Individual User Account** (Einzelbenutzerkonto) auswählen, wenn Sie das ASP.NET Core-Webanwendungsprojekt in Visual Studio erstellen, befindet sich der Code, der zur Anmeldung mit einem externen Anbieter benötigt wird, bereits im Projekt. Dies ist in Abbildung 9-3 dargestellt.

![Screenshot des Dialogfelds „Neue ASP.NET Core-Webanwendung“](./media/index/select-external-authentication-option.png)

**Abbildung 9-3.** Auswählen einer Option zur Verwendung der externen Authentifizierung beim Erstellen eines Webanwendungsprojekts

Zusätzlich zu den zuvor aufgeführten externen Authentifizierungsanbietern sind Pakete Dritter verfügbar, die Middleware zur Verwendung mehrerer externer Authentifizierungsanbieter bereitstellen. Eine Liste finden Sie im [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)-Repository auf GitHub.

Um besonderen Anforderungen gerecht zu werden, können Sie auch eigene Middleware zur externen Authentifizierung erstellen.

### <a name="authenticate-with-bearer-tokens"></a>Authentifizierung mit Bearertoken

Die Authentifizierung mit ASP.NET Core Identity (oder Identity plus externer Authentifizierunsanbieter) funktioniert für viele Webanwendungsszenarios einwandfrei, für die das Speichern von Benutzerinformationen in einem Cookie geeignet ist. In anderen Szenarios sind Cookies jedoch kein natürlicher Vorgang zum Beibehalten und Übertragen von Daten.

Beispielsweise verwenden Sie in einer ASP.NET Core-Web-API, die RESTful-Endpunkte verfügbar macht, auf die möglicherweise Einzelseitenanwendungen, native Clients oder auch andere Web-APIs zugreifen, stattdessen Bearertoken. Diese Anwendungstypen funktionieren nicht mit Cookies, können jedoch einfach ein Bearertoken abrufen und dieses in den Autorisierungsheader nachfolgender Anforderungen einfügen. Für die Tokenauthentifizierung unterstützt ASP.NET Core mehrere Optionen zur Verwendung von [OAuth 2.0](https://oauth.net/2/) und [OpenID Connect](https://openid.net/connect/).

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a>Authentifizierung mit einem OpenID Connect- und OAuth 2.0-Identitätsanbieter

Wenn Benutzerinformationen in Azure Active Directory oder einer anderen Identitätslösung gespeichert werden, die OpenID Connect oder OAuth 2.0 verwendet, können Sie das Paket **Microsoft.AspNetCore.Authentication.OpenIdConnect** für die Authentifizierung mithilfe des OpenID Connect-Workflows verwenden. Um sich z.B. beim Identity.Api-Microservice in eShopOnContainers zu authentifizieren, kann eine ASP.NET Core-Webanwendung, wie in folgendem vereinfachtem Beispiel in `Startup.cs` gezeigt, Middleware aus diesem Paket verwenden:

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

Beachten Sie, dass wenn Sie diesen Workflow verwenden, die ASP.NET Core Identity-Middleware nicht erforderlich ist, da der gesamte Speicher und die Authentifizierung der Benutzerinformationen vom Identitätsdienst behandelt werden.

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a>Ausstellen von Sicherheitstoken von einem ASP.NET Core-Dienst

Wenn Sie lieber Sicherheitstoken für lokale ASP.NET Core Identity-Benutzer ausstellen möchten, anstatt einen externen Identitätsanbieter zu verwenden, können Sie von einigen guten Bibliotheken von Drittanbietern profitieren.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) und [OpenIddict](https://github.com/openiddict/openiddict-core) sind OpenID Connect-Anbieter, die sich einfach in ASP.NET Core Identity integrieren lassen, damit Sie Sicherheitstoken von einem ASP.NET Core-Dienst ausstellen können. Die [IdentityServer4-Dokumentation](https://identityserver4.readthedocs.io/en/latest/) bietet detaillierte Anweisungen zur Verwendung der Bibliothek. Jedoch sind die grundlegenden Schritte zur Verwendung von IdentityServer4 zur Ausstellung von Token wie folgt.

1. Sie können UseIdentityServer in der Startup.Configure-Methode aufrufen, um IdentityServer4 der HTTP_Anforderungsverarbeitungspipeline hinzuzufügen. Dadurch kann die Bibliothek Anforderungen an OpenID Connect und OAuth2-Endpunkte wie „/connect/token“ verarbeiten

2. Sie konfigurieren IdentityServer4 in Startup.ConfigureServices, indem Sie services.AddIdentityServer aufrufen.

3. Sie konfigurieren Identitätsserver, indem Sie folgende Daten bereitstellen:

   - Die zu verwendenden [Anmeldeinformationen](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) für die Registrierung.

   - Die [Identitäts- und API-Ressourcen](https://identityserver4.readthedocs.io/en/latest/topics/resources.html), auf die Benutzer möglicherweise Zugriff anfordern:

      - API-Ressourcen stellen geschützte Daten oder Funktionen dar, auf die ein Benutzer mit einem Zugriffstoken zugreifen kann. Ein Beispiel einer API-Ressource wäre eine Web-API (oder ein Satz von APIs), für die die Autorisierung erforderlich ist.

      - Identitätsressourcen stellen Informationen (Ansprüche) dar, die einem Client zur Identifizierung eines Benutzers übergeben werden. Die Ansprüche können den Benutzernamen, die E-Mail-Adresse usw. beinhalten.

   - Die [Clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html), die eine Verbindung herstellen, um Token anzufordern.

   - Der Speichermechanismus für Benutzerinformationen, z.B. [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) oder eine Alternative.

Wenn Sie Clients und Ressourcen angeben, die IdentityServer4 verwenden sollen, können Sie eine <xref:System.Collections.Generic.IEnumerable%601>-Auflistung der geeigneten Typen an Methoden übergeben, die einen In-Memory-Client oder Ressourcenspeicher übernehmen. Für komplexere Szenarios können Sie auch Client- oder Ressourcenanbietertypen über eine Abhängigkeitsinjektion nutzen.

Eine Beispielkonfiguration für IdentityServer4 zur Verwendung von In-Memory-Ressourcen und -Clients, die von einem benutzerdefinierten IClientStore-Typen bereitgestellt werden, könnten wie folgt aussehen:

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a>Nutzen von Sicherheitstoken

Die Authentifizierung bei einem OpenID Connect-Endpunkt oder die Ausstellung Ihrer eigenen Sicherheitstoken deckt einige Szenarios ab. Was ist jedoch mit dem Dienst, der einfach nur den Zugriff für jene Benutzer einschränken muss, die über gültige Sicherheitstoken verfügen, die von einem anderen Dienst bereitgestellt wurden?

Für dieses Szenario ist die Middleware zur Authentifizierung, die JWT-Token behandelt, im **Microsoft.AspNetCore.Authentication.JwtBearer**-Paket verfügbar. JWT steht für „[JSON Web Token](https://tools.ietf.org/html/rfc7519)“ und ist ein allgemeines Sicherheitstokenformat (definiert von RFC 7519) zum Kommunizieren von Sicherheitsansprüchen. Vereinfacht sieht ein Beispiel zur Verwendung von Middleware zur Nutzung solcher Token etwa wie dieses Codefragment aus, das dem Ordering.Api-Microservice von eShopOnContainers entnommen ist.

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

Die Parameter hier sind:

- `Audience` stellt den Empfänger des eingehenden Tokens oder der Ressource dar, für die das Token den Zugriff erteilt. Wenn der in diesem Wert angegebene Parameter nicht mit dem Parameter im Token übereinstimmt, wird das Token abgelehnt.

- `Authority` ist die Adresse des Authentifizierungsservers, der Token ausgibt. Die Middleware zur JWT-Bearerauthentifizierung verwendet diesen URI, um den öffentlichen Schlüssel abzurufen, der zur Überprüfung der Tokensignatur verwendet werden kann. Die Middleware bestätigt auch, dass der `iss`-Parameter im Token mit diesem URI übereinstimmt.

Ein weiterer Parameter, `RequireHttpsMetadata`, ist für Testzwecke nützlich: Sie legen diesen Parameter auf FALSE fest, damit Sie Tests in Umgebungen durchführen können, in denen Sie keine Zertifikate besitzen. In realen Bereitstellungen dürfen JWT-Bearertoken immer nur über HTTPS übergeben werden.

Wenn diese Middleware vorhanden ist, werden JWT-Token automatisch aus Autorisierungsheadern extrahiert. Sie werden anschließend deserialisiert, überprüft (mithilfe der Werte in den Parametern `Audience` und `Authority`) und als Benutzerinformation gespeichert, auf die später durch MVC-Aktionen oder Autorisierungsfilter verwiesen werden soll.

Die Middleware für die JWT-Bearerauthentifizierung kann auch erweiterte Szenarios unterstützen, beispielsweise die Verwendung eines lokalen Zertifikats zur Überprüfung eines Tokens, wenn die Registrierungsstelle nicht verfügbar ist. Für dieses Szenario können Sie ein `TokenValidationParameters`-Objekt im `JwtBearerOptions`-Objekt angeben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Gemeinsames Verwenden von Cookies in mehreren Anwendungen** \
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- **Einführung in Identität** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Rick Anderson. Zweistufige Authentifizierung mit SMS** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- **Enabling authentication using Facebook, Google and other external providers (Ermöglichen der Authentifizierung mit Facebook, Google und anderen externen Anbietern)**  \
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- **Michell Anicas. An Introduction to OAuth 2 (Einführung in OAuth 2)**  \
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- **AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) \
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- **IdentityServer4. Offizielle Dokumentation** \
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
>[Zurück](../implement-resilient-applications/monitor-app-health.md)
>[Weiter](authorization-net-microservices-web-applications.md)
