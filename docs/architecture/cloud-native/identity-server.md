---
title: Identityserver für Native Cloud-apps
description: Architektur von Cloud Native .net-apps für Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 3797214685d20109b2c5dc4440ae5fc64dfddce6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841786"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="75282-103">Identityserver für Native Cloud-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="75282-103">IdentityServer for cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="75282-104">Identityserver ist ein Open-Source-Authentifizierungsserver, der die Standards OpenID Connect (oidc) und OAuth 2,0 für ASP.net Core implementiert.</span><span class="sxs-lookup"><span data-stu-id="75282-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="75282-105">Es ist so konzipiert, dass es eine gängige Methode zum Authentifizieren von Anforderungen an alle Ihre Anwendungen bietet, unabhängig davon, ob es sich um Web-, Native, Mobile oder API-Endpunkte handelt.</span><span class="sxs-lookup"><span data-stu-id="75282-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="75282-106">Identityserver kann zum Implementieren von einmaligem Anmelden (Single Sign-on, SSO) für mehrere Anwendungen und Anwendungs Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75282-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="75282-107">Sie kann verwendet werden, um tatsächliche Benutzer über Anmeldeformulare und ähnliche Benutzeroberflächen sowie die Dienst basierte Authentifizierung zu authentifizieren, die in der Regel die Tokenausstellung,-Überprüfung und-Verlängerung ohne Benutzeroberfläche umfasst.</span><span class="sxs-lookup"><span data-stu-id="75282-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="75282-108">Identityserver ist als anpassbare Lösung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="75282-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="75282-109">Jede Instanz wird in der Regel an eine einzelne Organisation und/oder eine Reihe von Anwendungsanforderungen angepasst.</span><span class="sxs-lookup"><span data-stu-id="75282-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="75282-110">Gängige Web-App-Szenarien</span><span class="sxs-lookup"><span data-stu-id="75282-110">Common web app scenarios</span></span>

<span data-ttu-id="75282-111">In der Regel müssen Anwendungen einige oder alle der folgenden Szenarios unterstützen:</span><span class="sxs-lookup"><span data-stu-id="75282-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="75282-112">Benutzer, die über einen Browser auf Webanwendungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75282-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="75282-113">Benutzer, die über browserbasierte apps auf Back-End-Web-APIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75282-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="75282-114">Menschliche Benutzer auf mobilen/nativen Clients, die auf Back-End-Web-APIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75282-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="75282-115">Andere Anwendungen, die auf Back-End-Web-APIs zugreifen (ohne einen aktiven Benutzer oder eine Benutzeroberfläche).</span><span class="sxs-lookup"><span data-stu-id="75282-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="75282-116">Jede Anwendung muss möglicherweise mit anderen Web-APIs interagieren, unter Verwendung ihrer eigenen Identität oder Delegierung an die Identität des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="75282-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

<span data-ttu-id="75282-117">![von Anwendungs Typen und-Szenarien](./media/application-types.png)
**Abbildung 8-1**.</span><span class="sxs-lookup"><span data-stu-id="75282-117">![Application types and scenarios](./media/application-types.png)
**Figure 8-1**.</span></span> <span data-ttu-id="75282-118">Anwendungs Typen und-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="75282-118">Application types and scenarios.</span></span>

<span data-ttu-id="75282-119">In jedem dieser Szenarien muss die verfügbar gemachte Funktionalität vor nicht autorisierter Verwendung geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="75282-119">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="75282-120">Dies erfordert mindestens eine Authentifizierung des Benutzers oder Prinzipals, der eine Anforderung für eine Ressource sendet.</span><span class="sxs-lookup"><span data-stu-id="75282-120">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="75282-121">Bei dieser Authentifizierung kann eines von mehreren gängigen Protokollen verwendet werden, z. b. SAML2p, WS-Fed oder OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="75282-121">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="75282-122">Die Kommunikation mit APIs verwendet in der Regel das OAuth2-Protokoll und seine Unterstützung für Sicherheits Token.</span><span class="sxs-lookup"><span data-stu-id="75282-122">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="75282-123">Durch die Trennung dieser wichtigen Sicherheitsaspekte und ihrer Implementierungsdetails aus den Anwendungen selbst wird die Konsistenz gewährleistet und die Sicherheit und Verwaltbarkeit verbessert.</span><span class="sxs-lookup"><span data-stu-id="75282-123">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="75282-124">Das Outsourcing dieser Bedenken an ein dediziertes Produkt wie identityserver unterstützt die Anforderung für jede Anwendung, diese Probleme selbst zu lösen.</span><span class="sxs-lookup"><span data-stu-id="75282-124">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="75282-125">Identityserver stellt Middleware zur Verfügung, die in einer ASP.net Core Anwendung ausgeführt wird und Unterstützung für OpenID Connect und OAuth2 hinzufügt (siehe [unterstützte Spezifikationen](http://docs.identityserver.io/en/latest/intro/specs.html)).</span><span class="sxs-lookup"><span data-stu-id="75282-125">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](http://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="75282-126">Organisationen erstellen Ihre eigene ASP.net Core-App mithilfe von identityserver-Middleware, die als STS für alle tokenbasierten Sicherheitsprotokolle fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="75282-126">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="75282-127">Die identityserver-Middleware macht Endpunkte verfügbar, um Standardfunktionen zu unterstützen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="75282-127">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="75282-128">Autorisieren (Authentifizieren des Endbenutzers)</span><span class="sxs-lookup"><span data-stu-id="75282-128">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="75282-129">Token (Programm gesteuertes Anfordern eines Tokens)</span><span class="sxs-lookup"><span data-stu-id="75282-129">Token (request a token programmatically)</span></span>
- <span data-ttu-id="75282-130">Ermittlung (Metadaten zum Server)</span><span class="sxs-lookup"><span data-stu-id="75282-130">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="75282-131">Benutzerinformationen (Abrufen von Benutzerinformationen mit einem gültigen Zugriffs Token)</span><span class="sxs-lookup"><span data-stu-id="75282-131">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="75282-132">Geräte Autorisierung (zum Starten der Geräte Fluss Autorisierung)</span><span class="sxs-lookup"><span data-stu-id="75282-132">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="75282-133">Introspection (tokenvalidierung)</span><span class="sxs-lookup"><span data-stu-id="75282-133">Introspection (token validation)</span></span>
- <span data-ttu-id="75282-134">Sperrung (tokenwiderruf)</span><span class="sxs-lookup"><span data-stu-id="75282-134">Revocation (token revocation)</span></span>
- <span data-ttu-id="75282-135">Sitzung beenden (einmaliges abmelden für alle apps Auslösung)</span><span class="sxs-lookup"><span data-stu-id="75282-135">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="75282-136">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="75282-136">Getting started</span></span>

<span data-ttu-id="75282-137">IdentityServer4 ist Open Source und kann kostenlos verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75282-137">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="75282-138">Sie können Sie mithilfe ihrer nuget-Pakete zu Ihren Anwendungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75282-138">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="75282-139">Das Hauptpaket ist [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) , das über 4 Millionen mal heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="75282-139">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="75282-140">Das Basispaket enthält keinen Code für die Benutzeroberfläche und unterstützt nur die Konfiguration im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="75282-140">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="75282-141">Um ihn mit einer Datenbank zu verwenden, benötigen Sie auch einen Datenanbieter wie [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) , der Entity Framework Core verwendet, um Konfigurations-und Betriebsdaten für identityserver zu speichern.</span><span class="sxs-lookup"><span data-stu-id="75282-141">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="75282-142">Für die Benutzeroberfläche können Sie Dateien aus dem [Schnellstart-UI-Repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) in Ihre ASP.net Core MVC-Anwendung kopieren, um Unterstützung für die Anmeldung und Abmeldung mithilfe der identityserver-Middleware hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75282-142">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="75282-143">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="75282-143">Configuration</span></span>

<span data-ttu-id="75282-144">Identityserver unterstützt verschiedene Arten von Protokollen und Anbietern sozialer Authentifizierung, die im Rahmen jeder benutzerdefinierten Installation konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="75282-144">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="75282-145">Dies erfolgt in der Regel in der `Startup` Klasse der ASP.net Core Anwendung in der `ConfigureServices`-Methode.</span><span class="sxs-lookup"><span data-stu-id="75282-145">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="75282-146">Die Konfiguration umfasst die Angabe der unterstützten Protokolle und der Pfade zu den Servern und Endpunkten, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75282-146">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="75282-147">In Abbildung 8-2 wird ein Beispiel für die Konfiguration des Benutzeroberflächen Projekts "IdentityServer4 Quick Start" gezeigt:</span><span class="sxs-lookup"><span data-stu-id="75282-147">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<inser here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="75282-148">**Abbildung 8-2**.</span><span class="sxs-lookup"><span data-stu-id="75282-148">**Figure 8-2**.</span></span> <span data-ttu-id="75282-149">Identityserver wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="75282-149">Configuring IdentityServer.</span></span>

<span data-ttu-id="75282-150">Identityserver hostet außerdem eine öffentliche Demosite, die zum Testen verschiedener Protokolle und Konfigurationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="75282-150">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="75282-151">Sie befindet sich unter [https://demo.identityserver.io/](https://demo.identityserver.io/) und enthält Informationen dazu, wie das Verhalten auf der Grundlage der bereitgestellten `client_id` konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="75282-151">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="75282-152">JavaScript-Clients</span><span class="sxs-lookup"><span data-stu-id="75282-152">JavaScript clients</span></span>

<span data-ttu-id="75282-153">Viele Cloud-native Anwendungen nutzen serverseitige APIs und umfassende Client Anwendungen (Single Page Applications, Spas) auf dem Front-End.</span><span class="sxs-lookup"><span data-stu-id="75282-153">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="75282-154">Identityserver sendet einen [JavaScript-Client](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html) (`oidc-client.js`) über NPM, der Spas hinzugefügt werden kann, um die Verwendung von identityserver für das anmelden, abmelden und die tokenbasierte Authentifizierung von Web-APIs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="75282-154">IdentityServer ships a [JavaScript client](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="75282-155">Verweise</span><span class="sxs-lookup"><span data-stu-id="75282-155">References</span></span>

- [<span data-ttu-id="75282-156">Identityserver-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="75282-156">IdentityServer documentation</span></span>](http://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="75282-157">Anwendungs Typen</span><span class="sxs-lookup"><span data-stu-id="75282-157">Application types</span></span>](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [<span data-ttu-id="75282-158">JavaScript-oidc-Client</span><span class="sxs-lookup"><span data-stu-id="75282-158">JavaScript OIDC client</span></span>](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="75282-159">[Zurück](azure-active-directory.md)
>[Weiter](security.md)</span><span class="sxs-lookup"><span data-stu-id="75282-159">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
