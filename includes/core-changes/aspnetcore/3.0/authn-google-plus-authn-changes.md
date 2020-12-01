---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032455"
---
### <a name="authentication-google-deprecated-and-replaced"></a>Authentifizierung: Google+ wurde als veraltet markiert und ersetzt.

Google hat ab 28. Januar 2019 damit begonnen, die Google+-Anmeldung für Apps [einzustellen](https://developers.google.com/+/api-shutdown).

#### <a name="change-description"></a>Änderungsbeschreibung

ASP.NET 4.x und ASP.NET Core verwendeten die Google+-Anmelde-APIs zum Authentifizieren von Google-Benutzerkonten in Web-Apps. Die betroffenen NuGet-Pakete sind [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) für ASP.NET Core und [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) für `Microsoft.Owin` mit ASP.NET Web Forms und MVC.

Die Ersetzungs-APIs von Google nutzen eine andere Datenquelle und ein anderes Format. Mit den unten aufgeführten Entschärfungen und Lösungen wird auf diese strukturellen Änderungen reagiert. Apps sollten überprüfen, ob die Daten selbst weiterhin die Anforderungen erfüllen. Beispielsweise können Namen, E-Mail-Adressen, Profilverknüpfungen und Profilfotos etwas andere Werte als zuvor bereitstellen.

#### <a name="version-introduced"></a>Eingeführt in Version

Alle Versionen. Diese Änderung ist extern von ASP.NET Core.

#### <a name="recommended-action"></a>Empfohlene Aktion

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>Owin mit ASP.NET Web Forms und MVC

Für `Microsoft.Owin` 3.1.0 und höher finden Sie [hier](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) eine vorübergehende Entschärfung. Apps sollten Tests mit der Entschärfung durchführen, um Änderungen am Datenformat zu überprüfen. Es gibt Pläne, `Microsoft.Owin` 4.0.1 mit einer Korrektur zu veröffentlichen. Apps, die eine frühere Version verwenden, sollten auf Version 4.0.1 aktualisiert werden.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1.x

Die Entschärfung in [Owin mit ASP.NET Web Forms und MVC](#owin-with-aspnet-web-forms-and-mvc) kann an ASP.NET Core 1.x angepasst werden. NuGet-Paketpatches sind nicht geplant, da Version 1.x das [Ende des Lebenszyklus](https://dotnet.microsoft.com/platform/support-policy) erreicht hat.

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2.x

Ersetzen Sie für `Microsoft.AspNetCore.Authentication.Google` Version 2.x den vorhandenen Aufruf von `AddGoogle` in `Startup.ConfigureServices` durch folgenden Code:

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

Die Februar-Patches 2.1 und 2.2 enthalten die vorherige Neukonfiguration als neuen Standard. Es ist kein Patch für ASP.NET Core 2.0 geplant, da diese Version das [Ende des Lebenszyklus](https://dotnet.microsoft.com/platform/support-policy) erreicht hat.

##### <a name="aspnet-core-30"></a>ASP.NET Core 3.0

Die für ASP.NET Core 2.x angegebene Entschärfung kann auch für ASP.NET Core 3.0 verwendet werden. In den nächsten Vorschauversionen für 3.0 wird das Paket `Microsoft.AspNetCore.Authentication.Google` möglicherweise entfernt. Benutzer würden stattdessen an `Microsoft.AspNetCore.Authentication.OpenIdConnect` weitergeleitet werden. Im folgenden Code wird das Ersetzen von `AddGoogle` durch `AddOpenIdConnect` in `Startup.ConfigureServices` veranschaulicht. Diese Ersetzung kann mit ASP.NET Core 2.0 und höher verwendet und bei Bedarf für ASP.NET Core 1.x angepasst werden.

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
