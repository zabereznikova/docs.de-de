---
title: Informationen zur Autorisierung in .NET-Microservices und Webanwendungen
description: 'Sicherheit in .NET-Microservices und Webanwendungen: Verschaffen Sie sich einen Überblick über die wichtigsten Autorisierungsoptionen in ASP.NET Core-Anwendungen – rollen- und richtlinienbasiert.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 27936a33ea2bb46cedb9d10ee47a2117e1843e14
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988205"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Informationen zur Autorisierung in .NET-Microservices und Webanwendungen

Nach der Authentifizierung müssen ASP.NET Core-Web-APIs den Zugriff autorisieren. Dieser Prozess ermöglicht einem Dienst die Zurverfügungstellung von APIs für einige authentifizierte Benutzer, jedoch nicht alle. Die [Autorisierung](/aspnet/core/security/authorization/introduction) kann basierend auf Benutzerrollen oder basierend auf einer benutzerdefinierten Richtlinie erfolgen, welche die Überprüfung von Ansprüchen oder anderen Heuristiken umfassen kann.

Die Einschränkung des Zugriffs auf eine ASP.NET Core-MVC-Route ist so einfach wie die Anwendung eines Authorize-Attributs auf die Aktionsmethode (oder auf die Controllerklasse, wenn für sämtliche Controlleraktionen eine Autorisierung erforderlich ist). Dies wird im folgenden Beispiel veranschaulicht:

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

Standardmäßig wird durch das Hinzufügen eines Authorize-Attributs ohne Parameter der Zugriff für diesen Controller oder diese Aktion auf authentifizierte Benutzer beschränkt. Wenn Sie eine API weiter beschränken möchten, sodass sie nur für bestimmte Benutzer verfügbar ist, kann das Attribut so erweitert werden, dass erforderliche Rollen oder Richtlinien angegeben werden, die von den Benutzern erfüllt werden müssen.

## <a name="implement-role-based-authorization"></a>Implementieren einer rollenbasierten Autorisierung

Die ASP.NET Core-Identität verfügt über ein integriertes Rollenkonzept. Neben Benutzern speichert die ASP.NET Core-Identität Informationen zu verschiedenen, von der Anwendung verwendeten Rollen und verfolgt mit, welche Benutzer welchen Rollen zugewiesen werden. Diese Zuweisungen können programmgesteuert mit dem `RoleManager`-Typ geändert werden, der Rollen in persistentem Speicher aktualisiert, und dem `UserManager`-Typ, der Benutzern Rollen gewähren oder sie widerrufen kann.

Wenn Sie eine Authentifizierung mit JWT-Bearertoken durchführen, füllt die Middleware für die Authentifizierung mit ASP.NET Core-JWT-Bearertoken die Rollen eines Benutzers basierend auf im Token gefundenen Rollenansprüchen auf. Wenn Sie den Zugriff auf eine MVC-Aktion oder einen MVC-Controller auf Benutzer in bestimmten Rollen beschränken möchten, können Sie, wie im folgenden Codefragment dargestellt, den Parameter „Roles“ in die Anmerkung (das Attribut) „Authorize“ einschließen:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

In diesem Beispiel können nur Benutzer mit der Rolle „Administrator“ oder „PowerUser“ auf APIs im ControlPanel-Controller zugreifen (z.B. zum Ausführen der SetTime-Aktion). Die ShutDown-API wird weiter eingeschränkt, damit nur Benutzer mit der Rolle „Administrator“ Zugriff haben.

Wenn ein Benutzer über mehrere Rollen verfügen soll, müssen Sie, wie im folgenden Beispiel dargestellt, mehrere Authorize-Attribute verwenden:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

In diesem Beispiel muss ein Benutzer folgende Voraussetzungen erfüllen, damit API1 aufgerufen wird:

- Er muss in der Rolle „Administrator“ *oder* „PowerUser“ sein, *und*

- er muss in der Rolle „RemoteEmployee“ sein, *und*

- er muss die Bedingungen eines benutzerdefinierten Handlers für die CustomPolicy-Autorisierung erfüllen.

## <a name="implement-policy-based-authorization"></a>Implementieren einer richtlinienbasierten Autorisierung

Benutzerdefinierte Autorisierungsregeln können auch mithilfe von [Autorisierungsrichtlinien](https://docs.asp.net/en/latest/security/authorization/policies.html) geschrieben werden. Dieser Abschnitt enthält einen Überblick. Weitere Informationen finden Sie unter [ASP.NET Authorization Workshop (ASP.NET-Autorisierungsworkshop)](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Benutzerdefinierte Autorisierungsrichtlinien werden in der Startup.ConfigureServices-Methode mithilfe der service.AddAuthorization-Methode registriert. Diese Methode wählt einen Delegaten für die Konfiguration eines AuthorizationOptions-Arguments aus.

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));

    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));

    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

Wie im Beispiel dargestellt wird, können Richtlinien unterschiedliche Arten von Anforderungen zugeordnet werden. Nach der Registrierung der Richtlinien können diese auf eine Aktion oder einen Controller angewendet werden, indem der Name der jeweiligen Richtlinie als Argument „Policy“ des Attributs „Authorize“ (z. B. `[Authorize(Policy="EmployeesOnly")]`) übergeben wird. Richtlinien können mehrere Anforderungen aufweisen, nicht nur eine (wie in diesen Beispielen zu sehen ist).

Im vorherigen Beispiel stellt der Aufruf von „AddPolicy“ nur eine alternative Möglichkeit für die Autorisierung nach Rollen dar. Wenn `[Authorize(Policy="AdministratorsOnly")]` auf eine API angewendet wird, können nur Benutzer mit der Rolle „Administrator“ darauf zugreifen.

Der zweite Aufruf von <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> veranschaulicht eine einfache Möglichkeit für die Anforderung, dass ein bestimmter Anspruch für den Benutzer vorhanden sein sollte. Bei der <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A>-Methode werden zudem optional erwartete Werte für den Anspruch übernommen. Wenn Werte angegeben sind, wird die Anforderung nur dann erfüllt, wenn der Benutzer sowohl über einen Anspruch des richtigen Typs als auch über einen der angegebenen Werte verfügt. Bei Verwendung der Middleware für die Authentifizierung mit JWT-Bearertoken stehen alle JWT-Eigenschaften als Benutzeransprüche zur Verfügung.

Die interessanteste der hier dargestellten Richtlinien ist die dritte `AddPolicy`-Methode, da diese eine benutzerdefinierte Autorisierungsanforderung verwendet. Durch die Verwendung von benutzerdefinierten Autorisierungsanforderungen verfügen Sie über sehr viel Kontrolle über die Vorgehensweise bei der Autorisierung. Damit dies funktioniert, müssen Sie folgende Typen implementieren:

- Einen Anforderungstyp, der von <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> abgeleitet wird und Felder enthält, in denen die Anforderungsdetails angegeben sind. Im Beispiel handelt es sich hierbei um ein Altersfeld für den `MinimumAgeRequirement`-Typ.

- Ein Handler, der <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601> implementiert, wobei „T“ der Typ von <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> ist, den der Handler bedienen kann. Der Handler muss die <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>-Methode implementieren, die überprüft, ob ein angegebener Kontext mit Informationen zum Benutzer die Anforderung erfüllt.

Wenn der Benutzer die Anforderung erfüllt, deutet ein Aufruf von `context.Succeed` darauf hin, dass der Benutzer autorisiert wurde. Wenn es mehrere Möglichkeiten für die Erfüllung einer Autorisierungsanforderung durch einen Benutzer gibt, können mehrere Handler erstellt werden.

Neben der Registrierung benutzerdefinierter Richtlinienanforderungen mit `AddPolicy`-Aufrufen müssen Sie auch über die Abhängigkeitsinjektion benutzerdefinierte Anforderungshandler registrieren (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).

Ein Beispiel für eine benutzerdefinierte Autorisierungsanforderung und einen Handler zur Überprüfung des Alters eines Benutzers (basierend auf einem `DateOfBirth`-Anspruch) ist in der [Dokumentation](https://docs.asp.net/en/latest/security/authorization/policies.html) zur ASP.NET Core-Autorisierung verfügbar.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **ASP.NET Core-Authentifizierung** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **ASP.NET Core-Autorisierung** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- **Rollenbasierte Autorisierung** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- **Benutzerdefinierte richtlinienbasierte Autorisierung** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](developer-app-secrets-storage.md)
