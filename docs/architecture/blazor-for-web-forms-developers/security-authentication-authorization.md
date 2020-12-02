---
title: 'Sicherheit: Authentifizierung und Autorisierung in ASP.net Web Forms und Blazor'
description: Erfahren Sie, wie Sie die Authentifizierung und Autorisierung in ASP.net Web Forms und behandeln Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 11/20/2020
ms.openlocfilehash: 0344960237a5d9da61eb0d85987c44e136f1be48
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509844"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a>Sicherheit: Authentifizierung und Autorisierung in ASP.NET Web Forms und Blazor 

Die Migration von einer ASP.net-Web Forms Anwendung zu Blazor erfordert fast sicherlich die Aktualisierung der Authentifizierung und Autorisierung, vorausgesetzt, die Anwendung hätte die Authentifizierung konfiguriert. In diesem Kapitel wird erläutert, wie Sie aus dem ASP.net Web Forms Universal Provider-Modell (für Mitgliedschaften, Rollen und Benutzerprofile) migrieren und wie Sie mit ASP.net Core Identität von Blazor apps arbeiten. In diesem Kapitel werden allgemeine Schritte und Überlegungen behandelt, die ausführlichen Schritte und Skripts finden Sie in der Dokumentation, auf die verwiesen wird.

## <a name="aspnet-universal-providers"></a>ASP.net universelle Anbieter

Seit ASP.NET 2,0 hat die ASP.net-Web Forms Plattform ein Anbieter Modell für eine Vielzahl von Features unterstützt, einschließlich der Mitgliedschaft. Der universelle Mitgliedschafts Anbieter wird zusammen mit dem optionalen Rollen Anbieter häufig mit ASP.net-Web Forms Anwendungen bereitgestellt. Er bietet eine robuste und sichere Möglichkeit zum Verwalten der Authentifizierung und Autorisierung, die noch heute gut funktionieren. Das aktuelle Angebot dieser universellen Anbieter steht als nuget-Paket [Microsoft. Aspnet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers)zur Verfügung.

Die universelle Anbieter arbeiten mit einem SQL-Datenbankschema, das Tabellen wie `aspnet_Applications` ,, `aspnet_Membership` und enthält `aspnet_Roles` `aspnet_Users` . Wenn Sie durch Ausführen des [aspnet_regsql.exe-Befehls](/previous-versions/ms229862(v=vs.140))konfiguriert werden, installieren die Anbieter Tabellen und gespeicherte Prozeduren, die alle erforderlichen Abfragen und Befehle bereitstellen, um mit den zugrunde liegenden Daten zu arbeiten. Das Datenbankschema und diese gespeicherten Prozeduren sind nicht mit neueren ASP.net Identity und ASP.net Core Identitäts Systemen kompatibel, sodass vorhandene Daten in das neue System migriert werden müssen. Abbildung 1 zeigt ein Beispiel für ein Tabellen Schema, das für universelle Anbieter konfiguriert wurde.

![Schema für universelle Anbieter](./media/security/membership-tables.png)

Der universelle Anbieter übernimmt Benutzer, Mitgliedschaft, Rollen und Profile. Benutzern werden globale eindeutige Bezeichner und grundlegende Informationen wie "UserID", "username" usw. in der `aspnet_Users` Tabelle gespeichert. Authentifizierungsinformationen, wie z. b. das Kennwort, das Kenn Wort Format, das Kennwort Salt, Sperr Indikatoren und Details usw. werden in der `aspnet_Membership` Tabelle gespeichert. Rollen bestehen einfach aus Namen und eindeutigen bezeichnerids, die Benutzern über die Zuordnungs Tabelle zugewiesen werden und `aspnet_UsersInRoles` eine m:n-Beziehung bereitstellen.

Wenn Ihr vorhandenes System zusätzlich zur Mitgliedschaft Rollen verwendet, müssen Sie die Benutzerkonten, die zugehörigen Kenn Wörter, die Rollen und die Rollen Mitgliedschaft in ASP.net Core Identität migrieren. Sie müssen wahrscheinlich auch Ihren Code aktualisieren, bei dem Sie zurzeit Rollen Überprüfungen durchführen, indem Sie if-Anweisungen verwenden, um stattdessen deklarative Filter, Attribute und/oder taghilfsprogramme zu nutzen. Am Ende dieses Kapitels werden die Migrations Überlegungen ausführlicher erläutert.

### <a name="authorization-configuration-in-web-forms"></a>Autorisierungs Konfiguration in Web Forms

Um den autorisierten Zugriff auf bestimmte Seiten in einer ASP.net-Web Forms Anwendung zu konfigurieren, geben Sie in der Regel an, dass anonyme Benutzer auf bestimmte Seiten oder Ordner nicht zugreifen können. Diese Konfiguration erfolgt in der web.config-Datei:

```xml
<?xml version="1.0"?>
<configuration>
    <system.web>
      <authentication mode="Forms">
        <forms defaultUrl="~/home.aspx" loginUrl="~/login.aspx"
          slidingExpiration="true" timeout="2880"></forms>
      </authentication>

      <authorization>
        <deny users="?" />
      </authorization>
    </system.web>
</configuration>
```

Der `authentication` Konfigurations Abschnitt richtet die Formular Authentifizierung für die Anwendung ein. Der `authorization` Abschnitt wird verwendet, um anonyme Benutzer nicht für die gesamte Anwendung zuzulassen. Sie können jedoch präzisetere Autorisierungs Regeln pro Standort bereitstellen und rollenbasierte Autorisierungs Überprüfungen anwenden.

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

Wenn die obige Konfiguration mit der ersten Konfiguration kombiniert wird, können anonyme Benutzer auf die Anmeldeseite zugreifen und die Website weite Einschränkung für nicht authentifizierte Benutzer überschreiben.

```xml
<location path="/admin">
  <system.web>
    <authorization>
      <allow roles="Administrators" />
      <deny users="*" />
    </authorization>
  </system.web>
</location>
```

Die obige Konfiguration, in Kombination mit den anderen, schränkt den Zugriff auf den `/admin` Ordner und alle darin enthaltenen Ressourcen auf Mitglieder der Rolle "Administratoren" ein. Diese Einschränkung kann auch angewendet werden, indem Sie eine separate `web.config` Datei innerhalb des Ordner Stamms platzieren `/admin` .

### <a name="authorization-code-in-web-forms"></a>Autorisierungs Code in Web Forms

Zusätzlich zum Konfigurieren des Zugriffs mithilfe von `web.config` können Sie den Zugriff und das Verhalten in Ihrer Web Forms Anwendung auch Programm gesteuert konfigurieren. Beispielsweise können Sie die Fähigkeit einschränken, bestimmte Vorgänge auszuführen oder bestimmte Daten basierend auf der Rolle des Benutzers anzuzeigen.

Dieser Code kann sowohl in der Code-Behind-Logik als auch auf der Seite selbst verwendet werden:

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

Zusätzlich zum Überprüfen der Mitgliedschaft in Benutzer Rollen können Sie auch feststellen, ob Sie authentifiziert sind (Dies ist jedoch oft besser durch die oben beschriebene standortbasierte Konfiguration möglich). Im folgenden finden Sie ein Beispiel für diesen Ansatz.

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if (!User.Identity.IsAuthenticated)
    {
        FormsAuthentication.RedirectToLoginPage();
    }
    if (!Roles.IsUserInRole(User.Identity.Name, "Administrators"))
    {
        MessageLabel.Text = "Only administrators can view this.";
        SecretPanel.Visible = false;
    }
}
```

Im obigen Code wird die rollenbasierte Zugriffs Steuerung (Role-Based Access Control, RBAC) verwendet, um zu bestimmen, ob bestimmte Elemente der Seite, z. b. `SecretPanel` , basierend auf der Rolle des aktuellen Benutzers sichtbar sind.

In der Regel konfigurieren ASP.net Web Forms Anwendungen die Sicherheit innerhalb der `web.config` Datei und fügen dann bei Bedarf zusätzliche Überprüfungen für `.aspx` Seiten und `.aspx.cs` zugehörige Code Behind-Dateien hinzu. Die meisten Anwendungen nutzen den universellen Mitgliedschafts Anbieter, häufig mit dem zusätzlichen Rollen Anbieter.

## <a name="aspnet-core-identity"></a>ASP.NET Core-Identität

Obwohl die Authentifizierung und Autorisierung weiterhin verwendet wird, verwendet ASP.net Core Identität im Vergleich zu den universellen Anbietern einen anderen Satz Abstraktionen und Annahmen. Beispielsweise unterstützt das neue Identitäts Modell die Authentifizierung von Drittanbietern, sodass sich Benutzer mit einem Social Media-Konto oder einem anderen vertrauenswürdigen Authentifizierungs Anbieter authentifizieren können. ASP.net Core Identity unterstützt die Benutzeroberfläche für häufig benötigte Seiten wie Login, Logout und Register. Er nutzt EF Core für den Datenzugriff und verwendet EF Core Migrationen, um das erforderliche Schema zu generieren, das für die Unterstützung des Datenmodells erforderlich ist. Diese [Einführung in die Identität auf ASP.net Core](/aspnet/core/security/authentication/identity) bietet einen guten Überblick darüber, was in ASP.net Core Identity enthalten ist und wie Sie mit der Arbeit beginnen können. Wenn Sie nicht bereits ASP.net Core Identität in Ihrer Anwendung und der zugehörigen Datenbank eingerichtet haben, wird Ihnen der Einstieg erleichtern.

### <a name="roles-claims-and-policies"></a>Rollen, Ansprüche und Richtlinien

Sowohl universelle Anbieter als auch ASP.net Core Identität unterstützen das Konzept der Rollen. Sie können Rollen für Benutzer erstellen und Rollen zuweisen. Benutzer können zu einer beliebigen Anzahl von Rollen gehören, und Sie können die Rollen Mitgliedschaft im Rahmen der Autorisierungs Implementierung überprüfen.

Zusätzlich zu den Rollen unterstützt ASP.net Core Identity die Konzepte von Ansprüchen und Richtlinien. Obwohl eine Rolle speziell einem Satz von Ressourcen entsprechen sollte, auf die ein Benutzer in dieser Rolle zugreifen kann, ist ein Anspruch einfach Teil der Identität eines Benutzers. Ein Anspruch ist ein Name-Wert-Paar, das den Betreff darstellt, nicht das, was der Betreff tun kann.

Es ist möglich, die Ansprüche eines Benutzers direkt zu überprüfen und anhand dieser Werte festzustellen, ob einem Benutzer Zugriff auf eine Ressource gewährt werden soll. Diese Überprüfungen werden jedoch häufig wiederholt und im gesamten System verstreut. Ein besserer Ansatz besteht darin, eine *Richtlinie* zu definieren.

Eine Autorisierungs Richtlinie besteht aus einer oder mehreren Anforderungen. Richtlinien werden als Teil der Autorisierungs Dienst Konfiguration in der- `ConfigureServices` Methode von registriert `Startup.cs` . Der folgende Code Ausschnitt konfiguriert z. b. eine Richtlinie mit dem Namen "canadiansonly", die die Anforderung hat, dass der Benutzer über den Anspruch "Country" mit dem Wert "Canada" verfügt.

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

[Weitere Informationen zum Erstellen von benutzerdefinierten Richtlinien finden Sie in der-Dokumentation](/aspnet/core/security/authorization/policies).

Unabhängig davon, ob Sie Richtlinien oder Rollen verwenden, können Sie angeben, dass eine bestimmte Seite in Blazor der Anwendung eine Rolle oder Richtlinie mit dem- `[Authorize]` Attribut erfordert, das mit der- `@attribute` Direktive angewendet wird.

Erfordert eine Rolle:

```csharp
@attribute [Authorize(Roles ="administrators")]
```

Das Verlangen einer Richtlinie muss erfüllt sein:

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

Wenn Sie Zugriff auf den Authentifizierungs Zustand, die Rollen oder Ansprüche eines Benutzers in Ihrem Code benötigen, gibt es zwei Hauptmethoden, um diese Funktionalität zu erreichen. Der erste besteht darin, den Authentifizierungs Status als kaskadierenden Parameter zu empfangen. Die zweite besteht darin, mithilfe eines eingefügten auf den Zustand zuzugreifen `AuthenticationStateProvider` . Die Details zu den einzelnen Ansätzen werden in der Dokumentation zur [ Blazor Sicherheit](/aspnet/core/blazor/security/)beschrieben.

Der folgende Code zeigt, wie der `AuthenticationState` als kaskadierenden Parameter empfangen wird:

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

Mit diesem Parameter können Sie den Benutzer mit dem folgenden Code aufrufen:

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

Der folgende Code zeigt, wie Sie einfügen `AuthenticationStateProvider` :

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

Wenn der Anbieter vorhanden ist, können Sie mit folgendem Code auf den Benutzer zugreifen:

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

**Hinweis:** Die `AuthorizeView` weiter unten in diesem Kapitel behandelte Komponente bietet eine deklarative Möglichkeit, um zu steuern, was ein Benutzer auf einer Seite oder Komponente sieht.

Zum Arbeiten mit Benutzern und Ansprüchen (in Blazor Server Anwendungen) müssen Sie möglicherweise auch eine `UserManager<T>` ( `IdentityUser` standardmäßig verwenden) einfügen, die Sie zum Auflisten und Ändern von Ansprüchen für einen Benutzer verwenden können. Fügen Sie zuerst den-Typ ein, und weisen Sie ihn einer Eigenschaft zu:

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

Verwenden Sie diese dann, um mit den Ansprüchen des Benutzers zu arbeiten. Im folgenden Beispiel wird gezeigt, wie ein Anspruch hinzugefügt und für einen Benutzer persistent gespeichert wird:

```csharp
private async Task AddCountryClaim()
{
    var authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
    var user = authState.User;
    var identityUser = await MyUserManager.FindByNameAsync(user.Identity.Name);

    if (!user.HasClaim(c => c.Type == ClaimTypes.Country))
    {
        // stores the claim in the cookie
        ClaimsIdentity id = new ClaimsIdentity();
        id.AddClaim(new Claim(ClaimTypes.Country, "Canada"));
        user.AddIdentity(id);

        // save the claim in the database
        await MyUserManager.AddClaimAsync(identityUser, new Claim(ClaimTypes.Country, "Canada"));
    }
}
```

Wenn Sie mit Rollen arbeiten müssen, gehen Sie wie folgt vor. Möglicherweise müssen Sie eine `RoleManager<T>` ( `IdentityRole` für den Standardtyp verwenden) einfügen, um die Rollen selbst aufzulisten und zu verwalten.

**Hinweis:** In Blazor Webassembly-Projekten müssen Sie Server-APIs bereitstellen, um diese Vorgänge auszuführen (anstatt `UserManager<T>` oder direkt zu verwenden `RoleManager<T>` ). Eine Blazor webassemblyclientanwendung verwaltet Ansprüche und/oder Rollen durch sicheres Aufrufen von API-Endpunkten, die für diesen Zweck verfügbar gemacht werden.

### <a name="migration-guide"></a>Migrationsleitfaden

Die Migration von ASP.net Web Forms und universellen Anbietern zu ASP.net Core Identity erfordert mehrere Schritte:

1. Erstellen ASP.net Core Identitätsdaten Bank Schemas in der Zieldatenbank
2. Migrieren von Daten aus einem universellen Anbieter Schema in ASP.net Core Identitäts Schema
3. Migrieren Sie die Konfiguration von `web.config` zu Middleware und Dienste, in der Regel in `Startup.cs`
4. Aktualisieren einzelner Seiten mithilfe von Steuerelementen und Bedingungen zur Verwendung von taghilfsprogrammen und neuen Identitäts-APIs.

Jeder dieser Schritte wird in den folgenden Abschnitten ausführlich erläutert.

### <a name="creating-the-aspnet-core-identity-schema"></a>Erstellen des ASP.net Core-Identitäts Schemas

Es gibt mehrere Möglichkeiten, die erforderliche Tabellenstruktur zu erstellen, die für die ASP.net Core Identität verwendet wird. Die einfachste Möglichkeit besteht darin, eine neue ASP.net Core-Webanwendung zu erstellen. Wählen Sie Webanwendung aus, und ändern Sie dann die Authentifizierung, sodass einzelne Benutzerkonten verwendet

![Neues Projekt mit einzelnen Benutzerkonten](./media/security/individual-user-accounts.png)

In der Befehlszeile können Sie das gleiche tun, indem Sie Ausführen `dotnet new webapp -au Individual` . Nachdem die App erstellt wurde, führen Sie Sie aus, und registrieren Sie sich auf der Website. Sie sollten eine Seite wie die folgende ausführen:

![Migrations Seite anwenden](./media/security/apply-migrations-page.png)

Klicken Sie auf die Schaltfläche Migrations anwenden, und die erforderlichen Datenbanktabellen sollten für Sie erstellt werden. Außerdem sollten die Migrations Dateien wie im folgenden dargestellt in Ihrem Projekt angezeigt werden:

![Migrations Dateien](./media/security/migration-files.png)

Mithilfe dieses Befehlszeilen Tools können Sie die Migration selbst ausführen, ohne die Webanwendung auszuführen:

```powershell
dotnet ef database update
```

Wenn Sie ein Skript zum Anwenden des neuen Schemas auf eine vorhandene Datenbank ausführen möchten, können Sie ein Skript für diese Migrationen von der Befehlszeile aus erstellen. Führen Sie diesen Befehl aus, um das Skript zu generieren:

```powershell
dotnet ef migrations script -o auth.sql
```

Mit dem obigen Befehl wird ein SQL-Skript in der Ausgabedatei erstellt `auth.sql` , das dann für die gewünschte Datenbank ausgeführt werden kann. Wenn Sie Probleme beim Ausführen von `dotnet ef` Befehlen haben, [Stellen Sie sicher, dass Sie die EF Core Tools auf Ihrem System installiert haben](/ef/core/miscellaneous/cli/dotnet).

Wenn Sie über zusätzliche Spalten in ihren Quell Tabellen verfügen, müssen Sie den besten Speicherort für diese Spalten im neuen Schema angeben. Im Allgemeinen sollten in der Tabelle gefundene Spalten `aspnet_Membership` der Tabelle zugeordnet werden `AspNetUsers` . Spalten in `aspnet_Roles` sollten zugeordnet werden `AspNetRoles` . Alle weiteren Spalten in der `aspnet_UsersInRoles` Tabelle werden der Tabelle hinzugefügt `AspNetUserRoles` .

Außerdem sollten Sie erwägen, zusätzliche Spalten in separaten Tabellen zu platzieren. Damit zukünftige Migrationen keine Anpassungen des Standard Identitäts Schemas berücksichtigen müssen.

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a>Migrieren von Daten von universellen Anbietern in ASP.net Core Identität

Wenn das Ziel Tabellen Schema vorhanden ist, besteht der nächste Schritt darin, die Benutzer-und Rollen Einträge zum neuen Schema zu migrieren. Eine komplette Liste der Schema Unterschiede, einschließlich der Spalten, denen neue Spalten zugeordnet werden, finden Sie [hier](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).

Wenn Sie Ihre Benutzer von der Mitgliedschaft zu den neuen Identitäts Tabellen migrieren möchten, sollten Sie [die in der Dokumentation beschriebenen Schritte](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)ausführen. Nachdem Sie diese Schritte und das bereitgestellte Skript ausgeführt haben, müssen die Benutzer Ihr Kennwort bei der nächsten Anmeldung ändern.

Es ist möglich, Benutzer Kennwörter zu migrieren, aber der Prozess ist viel mehr beteiligt. Wenn Sie möchten, dass Benutzer ihre Kenn Wörter im Rahmen des Migrations Vorgangs aktualisieren, und Sie dazu ermutigen, neue, eindeutige Kenn Wörter zu verwenden, ist es wahrscheinlich, dass die Gesamtsicherheit der Anwendung erhöht wird.

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a>Migrieren von Sicherheitseinstellungen von web.config zu Startup.cs

Wie bereits erwähnt, werden ASP.net-Mitgliedschafts-und Rollen Anbieter in der Datei der Anwendung konfiguriert `web.config` . Da ASP.net Core-apps nicht an IIS gebunden sind und ein separates System für die Konfiguration verwendet, müssen diese Einstellungen an anderer Stelle konfiguriert werden. Zum größten Teil wird ASP.net Core Identität in der-Datei konfiguriert `Startup.cs` . Öffnen Sie das zuvor erstellte Webprojekt (um das Schema der Identitäts Tabelle zu generieren), und überprüfen Sie die zugehörige `Startup.cs` Datei.

Die Standardmethode für die Konfiguration von Methoden fügt Unterstützung für EF Core und Identität hinzu:

```csharp
// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
}
```

Die `AddDefaultIdentity` -Erweiterungsmethode wird verwendet, um die Identität so zu konfigurieren, dass Sie die Standard- `ApplicationDbContext` und `IdentityUser` Frameworktypen verwendet. Wenn Sie einen benutzerdefinierten verwenden `IdentityUser` , achten Sie darauf, dass Sie den Typ hier angeben. Wenn diese Erweiterungs Methoden nicht in Ihrer Anwendung funktionieren, überprüfen Sie, ob Sie über die entsprechenden using-Anweisungen verfügen und dass Sie über die erforderlichen nuget-Paket Verweise verfügen. Beispielsweise sollte Ihr Projekt eine Version der `Microsoft.AspNetCore.Identity.EntityFrameworkCore` -und-Pakete enthalten, auf die `Microsoft.AspNetCore.Identity.UI` verwiesen wird.

Außerdem `Startup.cs` sollte in die erforderliche Middleware für die Website angezeigt werden. `UseAuthentication`Und `UseAuthorization` sollten vor allem und am richtigen Speicherort eingerichtet werden.

```csharp

// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
        app.UseDatabaseErrorPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
        // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
        app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
}
```

ASP.net Identity konfiguriert keinen anonymen oder rollenbasierten Zugriff auf Speicherorte von `Startup.cs` . Sie müssen ortsspezifische Autorisierungs Konfigurationsdaten zu Filtern in ASP.net Core migrieren. Notieren Sie sich, welche Ordner und Seiten solche Updates erfordern. Diese Änderungen werden im nächsten Abschnitt durchführen.

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a>Aktualisieren einzelner Seiten zur Verwendung ASP.net Core identitätsabstraktionen

Wenn Sie in Ihrer ASP.net Web Forms-Anwendung über `web.config` Einstellungen verfügen, um den Zugriff auf bestimmte Seiten oder Ordner auf anonyme Benutzer zu verweigern, würden Sie diese Änderungen migrieren, indem Sie das- `[Authorize]` Attribut zu diesen Seiten hinzufügen:

```razor
@attribute [Authorize]
```

Wenn Sie den Zugriff außer den Benutzern, die zu einer bestimmten Rolle gehören, weiterhin verweigert haben, würden Sie dieses Verhalten gleichermaßen migrieren, indem Sie ein Attribut hinzufügen, das eine Rolle angibt:

```razor
@attribute [Authorize(Roles ="administrators")]
```

Das- `[Authorize]` Attribut funktioniert nur für `@page` Komponenten, die über den Blazor Router erreicht werden. Das-Attribut funktioniert nicht mit untergeordneten Komponenten, die stattdessen verwenden sollten `AuthorizeView` .

Wenn Sie über Logik innerhalb des Seiten Markups verfügen, um zu bestimmen, ob Code für einen bestimmten Benutzer angezeigt werden soll, können Sie dies durch die `AuthorizeView` Komponente ersetzen. Die [Autorität "Autorität](/aspnet/core/blazor/security#authorizeview-component) anzeigen" zeigt selektiv die Benutzeroberfläche an, je nachdem, ob der Benutzer autorisiert ist, Sie anzuzeigen. Außerdem wird eine Variable verfügbar gemacht `context` , die für den Zugriff auf Benutzerinformationen verwendet werden kann.

```razor
<AuthorizeView>
    <Authorized>
        <h1>Hello, @context.User.Identity.Name!</h1>
        <p>You can only see this content if you are authenticated.</p>
    </Authorized>
    <NotAuthorized>
        <h1>Authentication Failure!</h1>
        <p>You are not signed in.</p>
    </NotAuthorized>
</AuthorizeView>
```

Sie können auf den Authentifizierungs Status innerhalb der prozeduralen Logik zugreifen, indem Sie auf den Benutzer von einem `Task<AuthenticationState` mit dem-Attribut konfigurierten zugreifen `[CascadingParameter]` Mit dieser Konfiguration erhalten Sie Zugriff auf den Benutzer, mit dem Sie ermitteln können, ob Sie authentifiziert sind und ob Sie zu einer bestimmten Rolle gehören. Wenn Sie eine Richtlinie prozedursch auswerten müssen, können Sie eine Instanz von einfügen `IAuthorizationService` und die- `AuthorizeAsync` Methode dafür aufrufen. Der folgende Beispielcode veranschaulicht, wie Sie Benutzerinformationen erhalten und einem autorisierten Benutzer gestatten, eine durch die Richtlinie eingeschränkte Aufgabe auszuführen `content-editor` .

```razor
@using Microsoft.AspNetCore.Authorization
@inject IAuthorizationService AuthorizationService

<button @onclick="@DoSomething">Do something important</button>

@code {
    [CascadingParameter]
    private Task<AuthenticationState> authenticationStateTask { get; set; }

    private async Task DoSomething()
    {
        var user = (await authenticationStateTask).User;

        if (user.Identity.IsAuthenticated)
        {
            // Perform an action only available to authenticated (signed-in) users.
        }

        if (user.IsInRole("admin"))
        {
            // Perform an action only available to users in the 'admin' role.
        }

        if ((await AuthorizationService.AuthorizeAsync(user, "content-editor"))
            .Succeeded)
        {
            // Perform an action only available to users satisfying the
            // 'content-editor' policy.
        }
    }
}
```

Der `AuthenticationState` erste muss als kaskadierenden Wert eingerichtet werden, bevor er an einen kaskadierenden Parameter wie diesen gebunden werden kann. Dies erfolgt in der Regel mithilfe der- `CascadingAuthenticationState` Komponente. Diese Konfiguration erfolgt in der Regel in `App.razor` :

```razor
<CascadingAuthenticationState>
    <Router AppAssembly="@typeof(Program).Assembly">
        <Found Context="routeData">
            <AuthorizeRouteView RouteData="@routeData"
                DefaultLayout="@typeof(MainLayout)" />
        </Found>
        <NotFound>
            <LayoutView Layout="@typeof(MainLayout)">
                <p>Sorry, there's nothing at this address.</p>
            </LayoutView>
        </NotFound>
    </Router>
</CascadingAuthenticationState>
```

## <a name="summary"></a>Zusammenfassung

Blazor verwendet das gleiche Sicherheitsmodell wie ASP.net Core, das ASP.net Core Identität ist. Die Migration von universellen Anbietern zur ASP.net Core Identität ist relativ unkompliziert, vorausgesetzt, dass nicht zu viele Anpassungen auf das ursprüngliche Datenschema angewendet wurden. Nachdem die Daten migriert wurden, ist die Arbeit mit der Authentifizierung und Autorisierung in- Blazor apps gut dokumentiert, mit konfigurierbarer und Programm gesteuerter Unterstützung für die meisten Sicherheitsanforderungen.

## <a name="references"></a>References

- [Einführung in die Identität auf ASP.net Core](/aspnet/core/security/authentication/identity)
- [Migrieren von der ASP.net-Mitgliedschafts Authentifizierung zu ASP.net Core 2,0-Identität](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [Migrieren von Authentifizierung und Identität zu ASP.net Core](/aspnet/core/migration/identity)
- [ASP.net Core Blazor Authentifizierung und Autorisierung](/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
>[Zurück](config.md)
>[Weiter](migration.md)
