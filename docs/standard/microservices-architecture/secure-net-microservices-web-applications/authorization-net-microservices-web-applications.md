---
title: Zur Autorisierung in .NET-Anwendungen Microservices und web
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Zur Autorisierung in .NET-Anwendungen Microservices und web"
keywords: Docker, Microservices, ASP.NET, Container
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Zur Autorisierung in .NET-Anwendungen Microservices und web

Nach der Authentifizierung müssen ASP.NET Core Web-APIs beim Autorisieren des Zugriffs aus. Dieser Prozess kann ein Dienst APIs stellen, einige authentifizierten Benutzern zur Verfügung, aber nicht alle. [Autorisierung](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) können basierend auf Rollen Benutzer durchgeführt oder basierend auf benutzerdefinierten Richtlinie u. u. enthalten Ansprüche oder andere Heuristik überprüfen.

Einschränken des Zugriffs auf eine ASP.NET Core MVC-Routen ist genauso einfach wie ein Authorize-Attribut zur Aktionsmethode (oder die Controller-Klasse, wenn Aktionen des Controllers Autorisierung erfordern), als gezeigt im folgenden Beispiel wird angewendet:

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

Standardmäßig wird das Hinzufügen eines Attributs autorisieren ohne Parameter Zugriff auf authentifizierte Benutzer für diesen Controller oder eine Aktion beschränkt. Eine API zur Verfügung steht nur für bestimmte Benutzer weiter einschränken möchten, kann das Attribut erweitert werden, um die erforderlichen Rollen oder Richtlinien, die Benutzer erfüllen müssen, angeben.

## <a name="implementing-role-based-authorization"></a>Implementieren der rollenbasierten Autorisierung

ASP.NET Core Identität verfügt über ein integriertes Rollenkonzept. Zusätzlich zu Benutzern ASP.NET Core Identity speichert Informationen zu verschiedenen Rollen, die von der Anwendung verwendeten und verfolgt die Benutzer, welche Rollen zugewiesen sind. Diese Aufgaben können programmgesteuert mit dem RoleManager-Typ (die Rollen im persistenten Speicher aktualisiert werden) und UserManager-Typ (die kann zuweisen bzw. Aufheben der Zuweisung von Benutzern aus Rollen) geändert werden.

Wenn Sie mit JWT-trägertoken authentifiziert werden, füllt der trägerauthentifizierungsmiddleware ASP.NET Core JWT Rollen eines Benutzers, die basierend auf Rollenansprüche im Token nicht gefunden. Um den Zugriff auf eine MVC-Aktion oder ein Controller aus, um Benutzer zu bestimmten Rollen einschränken möchten, können Sie einen Parameter für die Rollen im Autorisierungsheader, einschließen, wie im folgenden Beispiel gezeigt:

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

In diesem Beispiel können nur Benutzer in den Administrator oder PowerUser Rollen APIs im Controller ControlPanel (z. B. das Ausführen der Aktion SetTime) zugreifen. Die ShutDown-API wird weiter eingeschränkt, für den Zugriff nur für Benutzer in der Rolle "Administrator".

Verwenden Sie dahingehend, dass ein Benutzer in mehreren Rollen sein, mehrere autorisieren Attribute aus, wie im folgenden Beispiel gezeigt:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

In diesem Beispiel müssen zum Aufrufen von API1, ein Benutzer:

-   In der Administrator werden *oder* Rolle "PowerUser" *und*

-   Werden in der Rolle RemoteEmployee *und*

-   Erfüllen Sie einen benutzerdefinierten Handler für die CustomPolicy Autorisierung an.

## <a name="implementing-policy-based-authorization"></a>Implementieren von Autorisierung richtlinienbasierten

Benutzerdefinierte Autorisierungsregeln können auch mit geschrieben werden [Autorisierungsrichtlinien](https://docs.asp.net/en/latest/security/authorization/policies.html). In diesem Abschnitt bieten wir eine Übersicht über. Weitere Details finden Sie in der Onlinehilfe im [ASP.NET Autorisierung Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Benutzerdefinierte Autorisierungsrichtlinien werden in der Startup.ConfigureServices-Methode, die mit dem Dienst registriert. AddAuthorization-Methode. Diese Methode nimmt ein Delegat, der ein Argument AuthorizationOptions konfiguriert.

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

Wie im Beispiel gezeigt, können Richtlinien für verschiedene Arten von Anforderungen zugeordnet werden. Nachdem die Richtlinien registriert werden, sie können angewendet werden auf eine Aktion oder ein Domänencontroller durch die Übergabe von der Richtlinie namens als das richtlinienargument des Authorize-Attribut (z. B. \[Authorize(Policy="EmployeesOnly")\]) können Richtlinien verfügen. mehrere Anforderungen, die nicht nur eines (wie in diesen Beispielen gezeigt).

Im vorherigen Beispiel ist der erste Aufruf der AddPolicy nur eine alternative zum Autorisieren von Rolle. Wenn \[Authorize(Policy="AdministratorsOnly")\] auf einer API angewendet wird, nur Benutzer in der Rolle "Administrator" darauf zugreifen.

Der zweite Aufruf von AddPolicy veranschaulicht eine einfache Möglichkeit, die erfordern, dass ein bestimmter Anspruch für den Benutzer vorhanden sein sollte. Die RequireClaim-Methode nimmt auch optional erwarteten Werte für den Anspruch. Wenn Werte angegeben sind, wird die Anforderung erfüllt, nur dann, wenn der Benutzer sowohl einen Anspruch mit dem richtigen Typ und die angegebenen Werte verfügen. Bei Verwendung der JWT-trägerauthentifizierungsmiddleware werden alle JWT-Eigenschaften als Benutzeransprüche verfügbar sein.

Die interessanteste Richtlinie, die hier gezeigten ist in der dritten AddPolicy-Methode auf, da es sich um einen benutzerdefinierten Autorisierungs-Anforderung verwendet. Mithilfe von benutzerdefinierten autorisierungsanforderungen haben Sie viel Steuerung wie Autorisierung ausgeführt wird. Damit dies funktioniert müssen Sie diese Typen implementieren:

-   Ein Anforderungstyp, die IAuthorizationRequirement abgeleitet und enthält Felder, die die Details der Anforderung angegeben. Im Beispiel ist dies ein Altersfeld für den Typ der Beispiel-MinimumAgeRequirement.

-   Ein Handler, der implementiert AuthorizationHandler&lt;T&gt;, wobei T der Typ des IAuthorizationRequirement ist, die der Ereignishandler erfüllen kann. Der Handler muss die Methode HandleRequirementAsync implementieren, die überprüft, ob die Anforderung erfüllt, die ein angegebenen Kontext, der Informationen über den Benutzer enthält.

Wenn der Benutzer die Anforderung, die einen Aufruf von Kontext erfüllt werden. Wird erfolgreich anzugeben, dass der Benutzer autorisiert ist. Wenn es mehrere Möglichkeiten gibt, dass ein Benutzer eine autorisierungsanforderung erfüllen möglicherweise mehrere Handler erstellt werden können.

Zusätzlich zum Registrieren von Anforderungen der benutzerdefinierten Richtlinie mit AddPolicy aufrufen, müssen Sie auch zum Registrieren des benutzerdefinierten Anforderung Handler über Abhängigkeiteneinschleusung (Services. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).

Ein Beispiel eines benutzerdefinierten Autorisierungs-Anforderung und die Ereignishandler für die Überprüfung des Benutzers Age (auf der Grundlage eines Anspruchs DateOfBirth) ist verfügbar in der ASP.NET Core [Autorisierung Dokumentation](https://docs.asp.net/en/latest/security/authorization/policies.html).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **ASP.NET Core Authentifizierung**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **ASP.NET Core Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **Rollenbasierte Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **Benutzerdefinierte Richtlinie basierende Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Developer-app-Kennwörter-storage.md)
