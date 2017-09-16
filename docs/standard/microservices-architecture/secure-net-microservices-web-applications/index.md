---
title: Sichern von .NET-Microservices und Webanwendungen
description: ".NET Microservices-Architektur für .NET-Containeranwendungen | Sichern von .NET-Microservices und Webanwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 0bc9fe2975dc1c72f6dbe551c4ec74d7d51e69af
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---
# <a name="securing-net-microservices-and-web-applications"></a>Sichern von .NET-Microservices und Webanwendungen

Für Ressourcen und APIs, die durch einen Dienst verfügbar gemacht wurden, ist es oft notwendig, dass diese auf bestimmte vertrauenswürdige Benutzer oder Clients beschränkt werden. Der erste Schritt zur Durchführung dieser Entscheidungen über die Vertrauenswürdigkeit auf API-Ebene ist die Authentifizierung. Die Authentifizierung ist der Prozess, um die Identität eines Benutzers sicher zu ermitteln.

In Microservice-Szenarios wird die Authentifizierung in der Regel zentral verarbeitet. Wenn Sie ein API-Gateway verwenden, ist dieses Gateway ein guter Ort, um die Authentifizierung durchzuführen, so wie in Abbildung 11-1 dargestellt. Wenn Sie nach diesem Ansatz vorgehen, stellen Sie sicher, dass die einzelnen Microservices nicht direkt (ohne das API-Gateway) erreicht werden können, außer es kann zusätzliche Sicherheit garantiert werden, um Benachrichtigen danach zu authentifizieren, ob sie vom Gateway stammen oder nicht.

![](./media/image1.png)

**Abbildung 11-1**. Zentrale Authentifizierung mit einem API-Gateway

Wenn auf Dienste direkt zugegriffen werden kann, kann ein Authentifizierungsdienst wie Azure Active Directory oder ein dedizierter Authentifizierungs-Microservice, der als Sicherheitstokendienst (STS) fungiert, zum Authentifizieren von Benutzern verwendet werden. Entscheidungen über die Vertrauenswürdigkeit werden zwischen Diensten mit Sicherheitstoken oder Cookies freigegeben. (Diese können bei Bedarf zwischen Anwendungen in ASP.NET Core mit [Datenschutzdiensten](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications) freigegeben werden.) Dieses Muster ist in Abbildung 11-2 dargestellt.

![](./media/image2.png)

**Abbildung 11-2**. Authentifizierung durch Identitäts-Microservice; das Vertrauen ist mithilfe eines Autorisierungstokens freigegeben.

## <a name="authenticating-using-aspnet-core-identity"></a>Authentifizierung mit ASP.NET Core Identity

Der primäre Mechanismus in ASP.NET Core zur Identifizierung eines Anwendungsbenutzers ist das Mitgliedschaftssystem [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity). ASP.NET Core Identity speichert Benutzerinformationen (einschließlich Anmeldeinformationen, Rollen und Ansprüche) in einem Datenspeicher, der vom Entwickler konfiguriert wurde. Normalerweise ist der ASP.NET Core Identity-Datenspeicher ein Entity Framework-Speicher, der im Microsoft.AspNetCore.Identity.EntityFrameworkCore-Paket bereitgestellt wird. Jedoch können benutzerdefinierte Speicher oder andere Pakete von Drittanbietern zum Speichern von Identitätsinformationen in Azure Table Storage, DocumentDB oder anderen Speicherorten verwendet werden.

Der folgende Code wird aus der Projektvorlage der ASP.NET Core-Webanwendung genommen, für die eine einzelne Benutzerkontoauthentifizierung ausgewählt ist. Er stellt dar, wie ASP.NET Core Identiy mithilfe von EntityFramework.Core in der Startup.ConfigureServices-Methode konfiguriert wird.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

Sobald ASP.NET Core Identity konfiguriert ist, aktivieren Sie den Dienst, indem Sie „app.UseIdentity“ in der Startup.Configure-Methode des Diensts aufrufen.

Durch die Verwendung von ASP.NET Code Identity sind mehrere Szenarios möglich:

-   Erstellen Sie neue Benutzerinformationen mithilfe des UserManager-Typs (userManager.CreateAsync).

-   Authentifizieren Sie Benutzer mithilfe des SignInManager-Typs. Sie können „signInManager.SignInAsync“ verwenden, um sich direkt anzumelden, oder „signInManager.PasswordSignInAsync“, um zu bestätigen, dass das Kennwort des Benutzers korrekt ist, und um diesen anschließend anzumelden.

-   Identifizieren Sie einen Benutzer auf Grundlage von Informationen, die in einem Cookie gespeichert sind (das von der ASP.NET Core Identity-Middleware gelesen wird), damit nachfolgende Anforderungen von einem Browser die Identität und Ansprüche eines angemeldeten Benutzers enthalten.

ASP.NET Core Identity unterstützt auch die [zweistufige Authentifizierung](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).

ASP.NET Core Identity ist eine empfohlene Lösung für Authentifizierungsszenarios, die einen Datenspeicher für lokale Benutzerdaten verwenden und die Identität zwischen Anforderungen mithilfe von Cookies (was typisch für MVC-Webanwendungen ist) beibehalten.

## <a name="authenticating-using-external-providers"></a>Authentifizierung mithilfe externer Anbieter

ASP.NET Core unterstützt auch die Verwendung von [externen Authentifizierungsanbietern](https://docs.microsoft.com/aspnet/core/security/authentication/social/), damit sich Benutzer über [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)-Flows anmelden können. Das bedeutet, dass sich Benutzer mithilfe von vorhandenen Authentifizierungsprozessen von Anbietern wie Microsoft, Google, Facebook oder Twitter anmelden können und diese Identitäten ASP.NET Core Identity in Ihrer Anwendung zuordnen können.

Für die Verwendung der externen Authentifizierung schließen Sie die entsprechende Authentifizierungsmiddleware in der HTTP-Pipeline zum Verarbeiten von Anforderungen ein. Diese Middleware ist für die Verarbeitung von Anforderungen verantwortlich, um URI-Routen vom Authentifizierungsanbieter zurückzugeben, um Identitätsinformationen zu erfassen und diese über die SignInManager.GetExternalLoginInfo-Methode verfügbar zu machen.

Beliebte externe Authentifizierungsanbieter sowie deren zugeordnete NuGet-Pakete sind unten dargestellt.

**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount

**Google:** Microsoft.AspNetCore.Authentication.Google

**Facebook:** Microsoft.AspNetCore.Authentication.Facebook

**Twitter:** Microsoft.AspNetCore.Authentication.Twitter

In jedem Fall wird die Middleware mit einem Aufruf auf eine Registrierungsmethode registriert. Dieser Aufruf ähnelt app.Use{ExternalProvider}Authentication in Startup.Configure. Diese Registrierungsmethoden nehmen ein Options-Objekt, das je nach Anbieter eine Anwendungs-ID sowie geheime Informationen (beispielsweise ein Kennwort) enthält. Externe Authentifizierungsanbieter erfordern, dass die Anwendung registriert ist (so wie in der [ASP.NET Core-Dokumentation beschrieben](https://docs.microsoft.com/aspnet/core/security/authentication/social/)), sodass sie den Benutzer darüber informieren können, welche Anwendung Zugriff auf ihre Identität anfordert.

Sobald die Middleware in Startup.Configure registriert ist, können Sie Benutzer auffordern, sich von einer beliebigen Controlleraktion aus anzumelden. Um dies zu ermöglichen, erstellen Sie ein AuthenticationProperties-Objekt, das den Namen und die Umleitungs-URL des Authentifizierungsanbieters enthält. Sie geben anschließend eine „Challenge“-Antwort zurück, die das AuthenticationProperties-Objekt übergibt. Im folgenden Code ist ein Beispiel dafür dargestellt.

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

Wenn Sie die Authentifizierungsoption **Individual User Account** (Einzelbenutzerkonto) auswählen, wenn Sie das ASP.NET Code-Webanwendungsprojekt in Visual Studio erstellen, befindet sich der Code, der zur Anmeldung mit einem externen Anbieter benötigt wird, bereits im Projekt. Dies ist in Abbildung 11-3 dargestellt.

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

**Abbildung 11-3**. Auswählen einer Option zur Verwendung der externen Authentifizierung beim Erstellen eines Webanwendungsprojekts

Zusätzlich zu den zuvor aufgeführten externen Authentifizierungsanbietern sind Pakete Dritter verfügbar, die Middleware zur Verwendung mehrerer externer Authentifizierungsanbieter bereitstellen. Eine Liste finden Sie im [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)-Repository auf GitHub.

Es ist natürlich auch möglich, Ihre eigene Middleware für die externe Authentifizierung zu erstellen.

## <a name="authenticating-with-bearer-tokens"></a>Authentifizierung mit Bearertoken

Die Authentifizierung mit ASP.NET Core Identity (oder Identity plus externer Authentifizierunsanbieter) funktioniert für viele Webanwendungsszenarios einwandfrei, für die das Speichern von Benutzerinformationen in einem Cookie geeignet ist. In anderen Szenarios sind Cookies jedoch kein natürlicher Vorgang zum Beibehalten und Übertragen von Daten.

Beispielsweise verwenden Sie in einer ASP.NET Core-Web-API, die RESTful-Endpunkte verfügbar macht, auf die möglicherweise Einzelseitenanwendungen, native Clients oder auch andere Web-APIs zugreifen, stattdessen Bearertoken. Diese Anwendungstypen funktionieren nicht mit Cookies, können jedoch einfach ein Bearertoken abrufen und dieses in den Autorisierungsheader nachfolgender Anforderungen einfügen. Für die Tokenauthentifizierung unterstützt ASP.NET Core mehrere Optionen zur Verwendung von [OAuth 2.0](https://oauth.net/2/) und [OpenID Connect](http://openid.net/connect/).

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a>Authentifizierung mit einem OpenID Connect- und OAuth 2.0-Identitätsanbieter

Wenn Benutzerinformationen in Azure Active Directory oder einer anderen Identitätslösung gespeichert werden, die OpenID Connect oder OAuth 2.0 verwendet, können Sie das Paket „Microsoft.AspNetCore.Authentication.OpenIdConnect“ für die Authentifizierung mithilfe des OpenID Connect-Workflows verwenden. Um sich z.B. [für Azure Active Directory zu authentifizieren](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), kann eine ASP.NET Core-Webanwendung, wie in folgendem Beispiel gezeigt, Middleware aus diesem Paket verwenden:

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

Die Konfigurationswerte sind Azure Active Directory-Werte, die erstellt werden, wenn Ihre Anwendung [als Azure AD-Client registriert ist](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad). Eine einzelne Client-ID kann zwischen mehreren Microservices in einer Anwendung freigegeben werden, wenn sie alle Benutzer authentifizieren müssen, die über Azure Active Directory authentifiziert werden.

Beachten Sie, dass wenn Sie diesen Workflow verwenden, die ASP.NET Core Identity-Middleware nicht erforderlich ist, da der gesamte Speicher und die Authentifizierung der Benutzerinformationen von Azure Active Directory behandelt werden.

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a>Ausstellen von Sicherheitstoken von einem ASP.NET Core-Dienst

Wenn Sie lieber Sicherheitstoken für lokale ASP.NET Core Identity-Benutzer ausstellen möchten, anstatt einen externen Identitätsanbieter zu verwenden, können Sie von einigen guten Bibliotheken von Drittanbietern profitieren.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) und [OpenIddict](https://github.com/openiddict/openiddict-core) sind OpenID Connect-Anbieter, die sich einfach in ASP.NET Core Identity integrieren lassen, damit Sie Sicherheitstoken von einem ASP.NET Core-Dienst ausstellen können. Die [IdentityServer4-Dokumentation](https://identityserver4.readthedocs.io/en/release/) bietet detaillierte Anweisungen zur Verwendung der Bibliothek. Jedoch sind die grundlegenden Schritte zur Verwendung von IdentityServer4 zur Ausstellung von Token wie folgt.

1.  Sie können UseIdentityServer in der Startup.Configure-Methode aufrufen, um IdentityServer4 der HTTP_Anforderungsverarbeitungspipeline hinzuzufügen. Dadurch kann die Bibliothek Anforderungen an OpenID Connect und OAuth2-Endpunkte wie „/connect/token“ verarbeiten

2.  Sie konfigurieren IdentityServer4 in Startup.ConfigureServices, indem Sie services.AddIdentityServer aufrufen.

3.  Sie konfigurieren Identitätsserver, indem Sie folgende Daten bereitstellen:

-   Die zu verwendenden [Anmeldeinformationen](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) für die Registrierung.

-   Die [Identitäts- und API-Ressourcen](https://identityserver4.readthedocs.io/en/release/topics/resources.html), auf die Benutzer möglicherweise Zugriff anfordern:

<!-- -->

-   API-Ressourcen stellen geschützte Daten oder Funktionen dar, auf die ein Benutzer mit einem Zugriffstoken zugreifen kann. Ein Beispiel einer API-Ressource wäre eine Web-API (oder ein Satz von APIs), für die die Autorisierung erforderlich ist.

-   Identitätsressourcen stellen Informationen (Ansprüche) dar, die einem Client zur Identifizierung eines Benutzers übergeben werden. Die Ansprüche können den Benutzernamen, die E-Mail-Adresse usw. beinhalten.

<!-- -->

-   Die [Clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html), die eine Verbindung herstellen, um Token anzufordern.

-   Der Speichermechanismus für Benutzerinformationen, z.B. [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) oder eine Alternative.

Wenn Sie Clients und Ressourcen angeben, die IdentityServer4 verwenden sollen, können Sie eine IEnumerable&lt;T&gt;-Auflistung der geeigneten Typen an Methoden übergeben, die einen In-Memory-Client oder Ressourcenspeicher übernehmen. Für komplexere Szenarios können Sie auch Client- oder Ressourcenanbietertypen über eine Abhängigkeitsinjektion nutzen.

Eine Beispielkonfiguration für IdentityServer4 zur Verwendung von In-Memory-Ressourcen und -Clients, die von einem benutzerdefinierten IClientStore-Typen bereitgestellt werden, könnten wie folgt aussehen:

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a>Nutzen von Sicherheitstoken

Die Authentifizierung bei einem OpenID Connect-Endpunkt oder die Ausstellung Ihrer eigenen Sicherheitstoken deckt einige Szenarios ab. Was ist jedoch mit dem Dienst, der einfach nur den Zugriff für jene Benutzer einschränken muss, die über gültige Sicherheitstoken verfügen, die von einem anderen Dienst bereitgestellt wurden?

Für dieses Szenario ist die Middleware zur Authentifizierung, die JWT-Token behandelt, im Microsoft.AspNetCore.Authentication.JwtBearer-Paket verfügbar. JWT steht für „[JSON Web Token](https://tools.ietf.org/html/rfc7519)“ und ist ein allgemeines Sicherheitstokenformat (definiert von RFC 7519) zum Kommunizieren von Sicherheitsansprüchen. Ein einfaches Beispiel zur Verwendung von Middleware, um Token wie diese zu nutzen, sieht möglicherweise wie folgt aus. Dieser Code muss vor Aufrufen auf die ASP.NET Core-MVC-Middleware (app.UseMvc) stehen.

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

Die Parameter hier sind:

-   „Audience“ stellt den Empfänger des eingehenden Tokens oder der Ressource dar, für die das Token den Zugriff erteilt. Wenn der in diesem Wert angegebene Parameter nicht mit dem aud-Parameter im Token übereinstimmt, wird das Token abgelehnt.

-   „Authority“ ist die Adresse des Authentifizierungsservers, der Token ausgibt. Die Middleware zur JWT-Bearerauthentifizierung verwendet diesen URI, um den öffentlichen Schlüssel abzurufen, der zur Überprüfung der Tokensignatur verwendet werden kann. Die Middleware bestätigt auch, dass der iss-Parameter im Token mit diesem URI übereinstimmt.

-   „AutomaticAuthenticate“ ist ein boolescher Wert, der angibt, ob der vom Token definierte Benutzer automatisch angemeldet werden soll.

Ein weiterer Parameter, „RequireHttpsMetadata“, wird in diesem Beispiel nicht verwendet. Er ist nützlich zu Testzwecken; Sie legen diesen Parameter auf FALSE fest, damit Sie Tests in Umgebungen durchführen können, in denen Sie keine Zertifikate verfügen. In realen Bereitstellungen dürfen JWT-Bearertoken immer nur über HTTPS übergeben werden.

Wenn diese Middleware vorhanden ist, werden JWT-Token automatisch aus Autorisierungsheadern extrahiert. Sie werden anschließend deserialisiert, überprüft (mithilfe der Werte in den Parametern „Audience“ und „Authority“) und als Benutzerinformation gespeichert, auf die später durch MVC-Aktionen oder Autorisierungsfilter verwiesen werden soll.

Die Middleware für die JWT-Bearerauthentifizierung kann auch erweiterte Szenarios unterstützen, beispielsweise die Verwendung eines lokalen Zertifikats zur Überprüfung eines Tokens, wenn die Registrierungsstelle nicht verfügbar ist. Für dieses Szenario können Sie ein TokenValidationParameters-Objekt im JwtBearerOptions-Objekt angeben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Sharing cookies between applications (Freigeben von Cookies zwischen Anwendungen)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)

-   **Introduction to Identity (Einführung in Identity)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Rick Anderson. Two-factor authentication with SMS (Zweistufige Authentifizierung mit SMS)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)

-   **Enabling authentication using Facebook, Google and other external providers (Zulassen der Authentifizierung mit Facebook, Google und anderen externen Anbietern)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)

-   **Michell Anicas. An Introduction to OAuth 2 (Eine Einführung in OAuth 2)**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

-   **AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   **Danny Strockis. Integrating Azure AD into an ASP.NET Core web app (Integrieren von Azure AD in die ASP.NET Core-Web-App)**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)

-   **IdentityServer4. Official documentation (Offizielle Dokumentation zu IdentityServer4)**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)


>[!div class="step-by-step"]
[Zurück] (../implement-resilient-applications/monitor-app-health.md) [Weiter] (authorization-net-microservices-web-applications.md)

