---
title: Informationen zur Autorisierung in .NET-Microservices und Webanwendungen
description: 'Sicherheit in .NET-Microservices und Webanwendungen: Verschaffen Sie sich einen Überblick über die wichtigsten Autorisierungsoptionen in ASP.NET Core-Anwendungen – rollen- und richtlinienbasiert.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: f6b69faceac9a9b4819212cc04f89080f3ddad56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501768"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="7211c-103">Informationen zur Autorisierung in .NET-Microservices und Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="7211c-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="7211c-104">Nach der Authentifizierung müssen ASP.NET Core-Web-APIs den Zugriff autorisieren.</span><span class="sxs-lookup"><span data-stu-id="7211c-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="7211c-105">Dieser Prozess ermöglicht einem Dienst die Zurverfügungstellung von APIs für einige authentifizierte Benutzer, jedoch nicht alle.</span><span class="sxs-lookup"><span data-stu-id="7211c-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="7211c-106">Die [Autorisierung](/aspnet/core/security/authorization/introduction) kann basierend auf Benutzerrollen oder basierend auf einer benutzerdefinierten Richtlinie erfolgen, welche die Überprüfung von Ansprüchen oder anderen Heuristiken umfassen kann.</span><span class="sxs-lookup"><span data-stu-id="7211c-106">[Authorization](/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="7211c-107">Die Einschränkung des Zugriffs auf eine ASP.NET Core-MVC-Route ist so einfach wie die Anwendung eines Authorize-Attributs auf die Aktionsmethode (oder auf die Controllerklasse, wenn für sämtliche Controlleraktionen eine Autorisierung erforderlich ist). Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7211c-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="7211c-108">Standardmäßig wird durch das Hinzufügen eines Authorize-Attributs ohne Parameter der Zugriff für diesen Controller oder diese Aktion auf authentifizierte Benutzer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7211c-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="7211c-109">Wenn Sie eine API weiter beschränken möchten, sodass sie nur für bestimmte Benutzer verfügbar ist, kann das Attribut so erweitert werden, dass erforderliche Rollen oder Richtlinien angegeben werden, die von den Benutzern erfüllt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7211c-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implement-role-based-authorization"></a><span data-ttu-id="7211c-110">Implementieren einer rollenbasierten Autorisierung</span><span class="sxs-lookup"><span data-stu-id="7211c-110">Implement role-based authorization</span></span>

<span data-ttu-id="7211c-111">Die ASP.NET Core-Identität verfügt über ein integriertes Rollenkonzept.</span><span class="sxs-lookup"><span data-stu-id="7211c-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="7211c-112">Neben Benutzern speichert die ASP.NET Core-Identität Informationen zu verschiedenen, von der Anwendung verwendeten Rollen und verfolgt mit, welche Benutzer welchen Rollen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7211c-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="7211c-113">Diese Zuweisungen können programmgesteuert mit dem `RoleManager`-Typ geändert werden, der Rollen in persistentem Speicher aktualisiert, und dem `UserManager`-Typ, der Benutzern Rollen gewähren oder sie widerrufen kann.</span><span class="sxs-lookup"><span data-stu-id="7211c-113">These assignments can be changed programmatically with the `RoleManager` type that updates roles in persisted storage, and the `UserManager` type that can grant or revoke roles from users.</span></span>

<span data-ttu-id="7211c-114">Wenn Sie eine Authentifizierung mit JWT-Bearertoken durchführen, füllt die Middleware für die Authentifizierung mit ASP.NET Core-JWT-Bearertoken die Rollen eines Benutzers basierend auf im Token gefundenen Rollenansprüchen auf.</span><span class="sxs-lookup"><span data-stu-id="7211c-114">If you're authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="7211c-115">Wenn Sie den Zugriff auf eine MVC-Aktion oder einen MVC-Controller auf Benutzer in bestimmten Rollen beschränken möchten, können Sie, wie im folgenden Codefragment dargestellt, den Parameter „Roles“ in die Anmerkung (das Attribut) „Authorize“ einschließen:</span><span class="sxs-lookup"><span data-stu-id="7211c-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize annotation (attribute), as shown in the following code fragment:</span></span>

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

<span data-ttu-id="7211c-116">In diesem Beispiel können nur Benutzer mit der Rolle „Administrator“ oder „PowerUser“ auf APIs im ControlPanel-Controller zugreifen (z.B. zum Ausführen der SetTime-Aktion).</span><span class="sxs-lookup"><span data-stu-id="7211c-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="7211c-117">Die ShutDown-API wird weiter eingeschränkt, damit nur Benutzer mit der Rolle „Administrator“ Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="7211c-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="7211c-118">Wenn ein Benutzer über mehrere Rollen verfügen soll, müssen Sie, wie im folgenden Beispiel dargestellt, mehrere Authorize-Attribute verwenden:</span><span class="sxs-lookup"><span data-stu-id="7211c-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="7211c-119">In diesem Beispiel muss ein Benutzer folgende Voraussetzungen erfüllen, damit API1 aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="7211c-119">In this example, to call API1, a user must:</span></span>

- <span data-ttu-id="7211c-120">Er muss in der Rolle „Administrator“ *oder* „PowerUser“ sein, *und*</span><span class="sxs-lookup"><span data-stu-id="7211c-120">Be in the Administrator *or* PowerUser role, *and*</span></span>

- <span data-ttu-id="7211c-121">er muss in der Rolle „RemoteEmployee“ sein, *und*</span><span class="sxs-lookup"><span data-stu-id="7211c-121">Be in the RemoteEmployee role, *and*</span></span>

- <span data-ttu-id="7211c-122">er muss die Bedingungen eines benutzerdefinierten Handlers für die CustomPolicy-Autorisierung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7211c-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implement-policy-based-authorization"></a><span data-ttu-id="7211c-123">Implementieren einer richtlinienbasierten Autorisierung</span><span class="sxs-lookup"><span data-stu-id="7211c-123">Implement policy-based authorization</span></span>

<span data-ttu-id="7211c-124">Benutzerdefinierte Autorisierungsregeln können auch mithilfe von [Autorisierungsrichtlinien](https://docs.asp.net/en/latest/security/authorization/policies.html) geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7211c-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="7211c-125">Dieser Abschnitt enthält einen Überblick.</span><span class="sxs-lookup"><span data-stu-id="7211c-125">This section provides an overview.</span></span> <span data-ttu-id="7211c-126">Weitere Informationen finden Sie unter [ASP.NET Authorization Workshop (ASP.NET-Autorisierungsworkshop)](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="7211c-126">For more information, see the [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="7211c-127">Benutzerdefinierte Autorisierungsrichtlinien werden in der Startup.ConfigureServices-Methode mithilfe der service.AddAuthorization-Methode registriert.</span><span class="sxs-lookup"><span data-stu-id="7211c-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="7211c-128">Diese Methode wählt einen Delegaten für die Konfiguration eines AuthorizationOptions-Arguments aus.</span><span class="sxs-lookup"><span data-stu-id="7211c-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="7211c-129">Wie im Beispiel dargestellt wird, können Richtlinien unterschiedliche Arten von Anforderungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7211c-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="7211c-130">Nach der Registrierung der Richtlinien können diese auf eine Aktion oder einen Controller angewendet werden, indem der Name der jeweiligen Richtlinie als Argument „Policy“ des Attributs „Authorize“ (z.B. `[Authorize(Policy="EmployeesOnly")]`) übergeben wird. Richtlinien können mehrere Anforderungen enthalten, nicht nur eine (wie in diesen Beispielen zu sehen ist).</span><span class="sxs-lookup"><span data-stu-id="7211c-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, `[Authorize(Policy="EmployeesOnly")]`) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="7211c-131">Im vorherigen Beispiel stellt der Aufruf von „AddPolicy“ nur eine alternative Möglichkeit für die Autorisierung nach Rollen dar.</span><span class="sxs-lookup"><span data-stu-id="7211c-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="7211c-132">Wenn `[Authorize(Policy="AdministratorsOnly")]` auf eine API angewendet wird, können nur Benutzer mit der Rolle „Administrator“ darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7211c-132">If `[Authorize(Policy="AdministratorsOnly")]` is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="7211c-133">Der zweite Aufruf von <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> veranschaulicht eine einfache Möglichkeit für die Anforderung, dass ein bestimmter Anspruch für den Benutzer vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="7211c-133">The second <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="7211c-134">Bei der <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A>-Methode werden zudem optional erwartete Werte für den Anspruch übernommen.</span><span class="sxs-lookup"><span data-stu-id="7211c-134">The <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="7211c-135">Wenn Werte angegeben sind, wird die Anforderung nur dann erfüllt, wenn der Benutzer sowohl über einen Anspruch des richtigen Typs als auch über einen der angegebenen Werte verfügt.</span><span class="sxs-lookup"><span data-stu-id="7211c-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="7211c-136">Bei Verwendung der Middleware für die Authentifizierung mit JWT-Bearertoken stehen alle JWT-Eigenschaften als Benutzeransprüche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7211c-136">If you're using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="7211c-137">Die interessanteste der hier dargestellten Richtlinien ist die dritte `AddPolicy`-Methode, da diese eine benutzerdefinierte Autorisierungsanforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7211c-137">The most interesting policy shown here is in the third `AddPolicy` method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="7211c-138">Durch die Verwendung von benutzerdefinierten Autorisierungsanforderungen verfügen Sie über sehr viel Kontrolle über die Vorgehensweise bei der Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="7211c-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="7211c-139">Damit dies funktioniert, müssen Sie folgende Typen implementieren:</span><span class="sxs-lookup"><span data-stu-id="7211c-139">For this to work, you must implement these types:</span></span>

- <span data-ttu-id="7211c-140">Einen Anforderungstyp, der von <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> abgeleitet wird und Felder enthält, in denen die Anforderungsdetails angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7211c-140">A Requirements type that derives from <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="7211c-141">Im Beispiel handelt es sich hierbei um ein Altersfeld für den `MinimumAgeRequirement`-Typ.</span><span class="sxs-lookup"><span data-stu-id="7211c-141">In the example, this is an age field for the sample `MinimumAgeRequirement` type.</span></span>

- <span data-ttu-id="7211c-142">Ein Handler, der <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601> implementiert, wobei „T“ der Typ von <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> ist, den der Handler bedienen kann.</span><span class="sxs-lookup"><span data-stu-id="7211c-142">A handler that implements <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, where T is the type of <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> that the handler can satisfy.</span></span> <span data-ttu-id="7211c-143">Der Handler muss die <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>-Methode implementieren, die überprüft, ob ein angegebener Kontext mit Informationen zum Benutzer die Anforderung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="7211c-143">The handler must implement the <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="7211c-144">Wenn der Benutzer die Anforderung erfüllt, deutet ein Aufruf von `context.Succeed` darauf hin, dass der Benutzer autorisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7211c-144">If the user meets the requirement, a call to `context.Succeed` will indicate that the user is authorized.</span></span> <span data-ttu-id="7211c-145">Wenn es mehrere Möglichkeiten für die Erfüllung einer Autorisierungsanforderung durch einen Benutzer gibt, können mehrere Handler erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7211c-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="7211c-146">Neben der Registrierung benutzerdefinierter Richtlinienanforderungen mit `AddPolicy`-Aufrufen müssen Sie auch über die Abhängigkeitsinjektion benutzerdefinierte Anforderungshandler registrieren (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span><span class="sxs-lookup"><span data-stu-id="7211c-146">In addition to registering custom policy requirements with `AddPolicy` calls, you also need to register custom requirement handlers via Dependency Injection (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span></span>

<span data-ttu-id="7211c-147">Ein Beispiel für eine benutzerdefinierte Autorisierungsanforderung und einen Handler zur Überprüfung des Alters eines Benutzers (basierend auf einem `DateOfBirth`-Anspruch) ist in der [Dokumentation](https://docs.asp.net/en/latest/security/authorization/policies.html) zur ASP.NET Core-Autorisierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7211c-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a `DateOfBirth` claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7211c-148">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7211c-148">Additional resources</span></span>

- <span data-ttu-id="7211c-149">**ASP.NET Core-Authentifizierung** </span><span class="sxs-lookup"><span data-stu-id="7211c-149">**ASP.NET Core Authentication** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="7211c-150">**ASP.NET Core-Autorisierung** </span><span class="sxs-lookup"><span data-stu-id="7211c-150">**ASP.NET Core Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- <span data-ttu-id="7211c-151">**Rollenbasierte Autorisierung** </span><span class="sxs-lookup"><span data-stu-id="7211c-151">**Role-based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- <span data-ttu-id="7211c-152">**Benutzerdefinierte richtlinienbasierte Autorisierung** </span><span class="sxs-lookup"><span data-stu-id="7211c-152">**Custom Policy-Based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
><span data-ttu-id="7211c-153">[Zurück](index.md)
>[Weiter](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="7211c-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
