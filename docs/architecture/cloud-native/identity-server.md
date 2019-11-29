---
title: Identityserver für Native Cloud-apps
description: Architektur von Cloud Native .net-apps für Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: e96395766d1a4b63815c10c2c90e35a8f7f9159d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568467"
---
# <a name="identityserver-for-cloud-native-applications"></a>Identityserver für Native Cloud-Anwendungen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Identityserver ist ein Open-Source-Authentifizierungsserver, der die Standards OpenID Connect (oidc) und OAuth 2,0 für ASP.net Core implementiert. Es ist so konzipiert, dass es eine gängige Methode zum Authentifizieren von Anforderungen an alle Ihre Anwendungen bietet, unabhängig davon, ob es sich um Web-, Native, Mobile oder API-Endpunkte handelt. Identityserver kann zum Implementieren von einmaligem Anmelden (Single Sign-on, SSO) für mehrere Anwendungen und Anwendungs Typen verwendet werden. Sie kann verwendet werden, um tatsächliche Benutzer über Anmeldeformulare und ähnliche Benutzeroberflächen sowie die Dienst basierte Authentifizierung zu authentifizieren, die in der Regel die Tokenausstellung,-Überprüfung und-Verlängerung ohne Benutzeroberfläche umfasst. Identityserver ist als anpassbare Lösung konzipiert. Jede Instanz wird in der Regel an eine einzelne Organisation und/oder eine Reihe von Anwendungsanforderungen angepasst.

## <a name="common-web-app-scenarios"></a>Gängige Web-App-Szenarien

In der Regel müssen Anwendungen einige oder alle der folgenden Szenarios unterstützen:

- Benutzer, die über einen Browser auf Webanwendungen zugreifen.
- Benutzer, die über browserbasierte apps auf Back-End-Web-APIs zugreifen.
- Menschliche Benutzer auf mobilen/nativen Clients, die auf Back-End-Web-APIs zugreifen.
- Andere Anwendungen, die auf Back-End-Web-APIs zugreifen (ohne einen aktiven Benutzer oder eine Benutzeroberfläche).
- Jede Anwendung muss möglicherweise mit anderen Web-APIs interagieren, unter Verwendung ihrer eigenen Identität oder Delegierung an die Identität des Benutzers.

![von Anwendungs Typen und-Szenarien](./media/application-types.png)
**Abbildung 8-1**. Anwendungs Typen und-Szenarien.

In jedem dieser Szenarien muss die verfügbar gemachte Funktionalität vor nicht autorisierter Verwendung geschützt werden. Dies erfordert mindestens eine Authentifizierung des Benutzers oder Prinzipals, der eine Anforderung für eine Ressource sendet. Bei dieser Authentifizierung kann eines von mehreren gängigen Protokollen verwendet werden, z. b. SAML2p, WS-Fed oder OpenID Connect. Die Kommunikation mit APIs verwendet in der Regel das OAuth2-Protokoll und seine Unterstützung für Sicherheits Token. Durch die Trennung dieser wichtigen Sicherheitsaspekte und ihrer Implementierungsdetails aus den Anwendungen selbst wird die Konsistenz gewährleistet und die Sicherheit und Verwaltbarkeit verbessert. Das Outsourcing dieser Bedenken an ein dediziertes Produkt wie identityserver unterstützt die Anforderung für jede Anwendung, diese Probleme selbst zu lösen.

Identityserver stellt Middleware zur Verfügung, die in einer ASP.net Core Anwendung ausgeführt wird und Unterstützung für OpenID Connect und OAuth2 hinzufügt (siehe [unterstützte Spezifikationen](http://docs.identityserver.io/en/latest/intro/specs.html)). Organisationen erstellen Ihre eigene ASP.net Core-App mithilfe von identityserver-Middleware, die als STS für alle tokenbasierten Sicherheitsprotokolle fungieren soll. Die identityserver-Middleware macht Endpunkte verfügbar, um Standardfunktionen zu unterstützen, einschließlich:

- Autorisieren (Authentifizieren des Endbenutzers)
- Token (Programm gesteuertes Anfordern eines Tokens)
- Ermittlung (Metadaten zum Server)
- Benutzerinformationen (Abrufen von Benutzerinformationen mit einem gültigen Zugriffs Token)
- Geräte Autorisierung (zum Starten der Geräte Fluss Autorisierung)
- Introspection (tokenvalidierung)
- Sperrung (tokenwiderruf)
- Sitzung beenden (einmaliges abmelden für alle apps Auslösung)

## <a name="getting-started"></a>Erste Schritte

IdentityServer4 ist Open Source und kann kostenlos verwendet werden. Sie können Sie mithilfe ihrer nuget-Pakete zu Ihren Anwendungen hinzufügen. Das Hauptpaket ist [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) , das über 4 Millionen mal heruntergeladen wurde. Das Basispaket enthält keinen Code für die Benutzeroberfläche und unterstützt nur die Konfiguration im Arbeitsspeicher. Um ihn mit einer Datenbank zu verwenden, benötigen Sie auch einen Datenanbieter wie [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) , der Entity Framework Core verwendet, um Konfigurations-und Betriebsdaten für identityserver zu speichern. Für die Benutzeroberfläche können Sie Dateien aus dem [Schnellstart-UI-Repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) in Ihre ASP.net Core MVC-Anwendung kopieren, um Unterstützung für die Anmeldung und Abmeldung mithilfe der identityserver-Middleware hinzuzufügen.

## <a name="configuration"></a>-Konfiguration

Identityserver unterstützt verschiedene Arten von Protokollen und Anbietern sozialer Authentifizierung, die im Rahmen jeder benutzerdefinierten Installation konfiguriert werden können. Dies erfolgt in der Regel in der `Startup` Klasse der ASP.net Core Anwendung in der `ConfigureServices`-Methode. Die Konfiguration umfasst die Angabe der unterstützten Protokolle und der Pfade zu den Servern und Endpunkten, die verwendet werden. In Abbildung 8-2 wird ein Beispiel für die Konfiguration des Benutzeroberflächen Projekts "IdentityServer4 Quick Start" gezeigt:

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
                options.ClientSecret = "<insert here>";
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

**Abbildung 8-2**. Identityserver wird konfiguriert.

Identityserver hostet außerdem eine öffentliche Demosite, die zum Testen verschiedener Protokolle und Konfigurationen verwendet werden kann. Sie befindet sich unter [https://demo.identityserver.io/](https://demo.identityserver.io/) und enthält Informationen dazu, wie das Verhalten auf der Grundlage der bereitgestellten `client_id` konfiguriert werden kann.

## <a name="javascript-clients"></a>JavaScript-Clients

Viele Cloud-native Anwendungen nutzen serverseitige APIs und umfassende Client Anwendungen (Single Page Applications, Spas) auf dem Front-End. Identityserver sendet einen [JavaScript-Client](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html) (`oidc-client.js`) über NPM, der Spas hinzugefügt werden kann, um die Verwendung von identityserver für das anmelden, abmelden und die tokenbasierte Authentifizierung von Web-APIs zu ermöglichen.

## <a name="references"></a>Verweise

- [Identityserver-Dokumentation](http://docs.identityserver.io/en/latest/)
- [Anwendungs Typen](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [JavaScript-oidc-Client](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html)

>[!div class="step-by-step"]
>[Zurück](azure-active-directory.md)
>[Weiter](security.md)
