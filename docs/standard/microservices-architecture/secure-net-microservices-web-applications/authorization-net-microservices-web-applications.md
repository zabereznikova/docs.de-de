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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="4ee6a-104">Zur Autorisierung in .NET-Anwendungen Microservices und web</span><span class="sxs-lookup"><span data-stu-id="4ee6a-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="4ee6a-105">Nach der Authentifizierung müssen ASP.NET Core Web-APIs beim Autorisieren des Zugriffs aus.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="4ee6a-106">Dieser Prozess kann ein Dienst APIs stellen, einige authentifizierten Benutzern zur Verfügung, aber nicht alle.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="4ee6a-107">[Autorisierung](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) können basierend auf Rollen Benutzer durchgeführt oder basierend auf benutzerdefinierten Richtlinie u. u. enthalten Ansprüche oder andere Heuristik überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="4ee6a-108">Einschränken des Zugriffs auf eine ASP.NET Core MVC-Routen ist genauso einfach wie ein Authorize-Attribut zur Aktionsmethode (oder die Controller-Klasse, wenn Aktionen des Controllers Autorisierung erfordern), als gezeigt im folgenden Beispiel wird angewendet:</span><span class="sxs-lookup"><span data-stu-id="4ee6a-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="4ee6a-109">Standardmäßig wird das Hinzufügen eines Attributs autorisieren ohne Parameter Zugriff auf authentifizierte Benutzer für diesen Controller oder eine Aktion beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="4ee6a-110">Eine API zur Verfügung steht nur für bestimmte Benutzer weiter einschränken möchten, kann das Attribut erweitert werden, um die erforderlichen Rollen oder Richtlinien, die Benutzer erfüllen müssen, angeben.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="4ee6a-111">Implementieren der rollenbasierten Autorisierung</span><span class="sxs-lookup"><span data-stu-id="4ee6a-111">Implementing role-based authorization</span></span>

<span data-ttu-id="4ee6a-112">ASP.NET Core Identität verfügt über ein integriertes Rollenkonzept.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="4ee6a-113">Zusätzlich zu Benutzern ASP.NET Core Identity speichert Informationen zu verschiedenen Rollen, die von der Anwendung verwendeten und verfolgt die Benutzer, welche Rollen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="4ee6a-114">Diese Aufgaben können programmgesteuert mit dem RoleManager-Typ (die Rollen im persistenten Speicher aktualisiert werden) und UserManager-Typ (die kann zuweisen bzw. Aufheben der Zuweisung von Benutzern aus Rollen) geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="4ee6a-115">Wenn Sie mit JWT-trägertoken authentifiziert werden, füllt der trägerauthentifizierungsmiddleware ASP.NET Core JWT Rollen eines Benutzers, die basierend auf Rollenansprüche im Token nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="4ee6a-116">Um den Zugriff auf eine MVC-Aktion oder ein Controller aus, um Benutzer zu bestimmten Rollen einschränken möchten, können Sie einen Parameter für die Rollen im Autorisierungsheader, einschließen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4ee6a-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

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

<span data-ttu-id="4ee6a-117">In diesem Beispiel können nur Benutzer in den Administrator oder PowerUser Rollen APIs im Controller ControlPanel (z. B. das Ausführen der Aktion SetTime) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="4ee6a-118">Die ShutDown-API wird weiter eingeschränkt, für den Zugriff nur für Benutzer in der Rolle "Administrator".</span><span class="sxs-lookup"><span data-stu-id="4ee6a-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="4ee6a-119">Verwenden Sie dahingehend, dass ein Benutzer in mehreren Rollen sein, mehrere autorisieren Attribute aus, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4ee6a-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="4ee6a-120">In diesem Beispiel müssen zum Aufrufen von API1, ein Benutzer:</span><span class="sxs-lookup"><span data-stu-id="4ee6a-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="4ee6a-121">In der Administrator werden *oder* Rolle "PowerUser" *und*</span><span class="sxs-lookup"><span data-stu-id="4ee6a-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="4ee6a-122">Werden in der Rolle RemoteEmployee *und*</span><span class="sxs-lookup"><span data-stu-id="4ee6a-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="4ee6a-123">Erfüllen Sie einen benutzerdefinierten Handler für die CustomPolicy Autorisierung an.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="4ee6a-124">Implementieren von Autorisierung richtlinienbasierten</span><span class="sxs-lookup"><span data-stu-id="4ee6a-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="4ee6a-125">Benutzerdefinierte Autorisierungsregeln können auch mit geschrieben werden [Autorisierungsrichtlinien](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="4ee6a-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="4ee6a-126">In diesem Abschnitt bieten wir eine Übersicht über.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-126">In this section we provide an overview.</span></span> <span data-ttu-id="4ee6a-127">Weitere Details finden Sie in der Onlinehilfe im [ASP.NET Autorisierung Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="4ee6a-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="4ee6a-128">Benutzerdefinierte Autorisierungsrichtlinien werden in der Startup.ConfigureServices-Methode, die mit dem Dienst registriert. AddAuthorization-Methode.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="4ee6a-129">Diese Methode nimmt ein Delegat, der ein Argument AuthorizationOptions konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="4ee6a-130">Wie im Beispiel gezeigt, können Richtlinien für verschiedene Arten von Anforderungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="4ee6a-131">Nachdem die Richtlinien registriert werden, sie können angewendet werden auf eine Aktion oder ein Domänencontroller durch die Übergabe von der Richtlinie namens als das richtlinienargument des Authorize-Attribut (z. B. \[Authorize(Policy="EmployeesOnly")\]) können Richtlinien verfügen. mehrere Anforderungen, die nicht nur eines (wie in diesen Beispielen gezeigt).</span><span class="sxs-lookup"><span data-stu-id="4ee6a-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="4ee6a-132">Im vorherigen Beispiel ist der erste Aufruf der AddPolicy nur eine alternative zum Autorisieren von Rolle.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="4ee6a-133">Wenn \[Authorize(Policy="AdministratorsOnly")\] auf einer API angewendet wird, nur Benutzer in der Rolle "Administrator" darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="4ee6a-134">Der zweite Aufruf von AddPolicy veranschaulicht eine einfache Möglichkeit, die erfordern, dass ein bestimmter Anspruch für den Benutzer vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="4ee6a-135">Die RequireClaim-Methode nimmt auch optional erwarteten Werte für den Anspruch.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="4ee6a-136">Wenn Werte angegeben sind, wird die Anforderung erfüllt, nur dann, wenn der Benutzer sowohl einen Anspruch mit dem richtigen Typ und die angegebenen Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="4ee6a-137">Bei Verwendung der JWT-trägerauthentifizierungsmiddleware werden alle JWT-Eigenschaften als Benutzeransprüche verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="4ee6a-138">Die interessanteste Richtlinie, die hier gezeigten ist in der dritten AddPolicy-Methode auf, da es sich um einen benutzerdefinierten Autorisierungs-Anforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="4ee6a-139">Mithilfe von benutzerdefinierten autorisierungsanforderungen haben Sie viel Steuerung wie Autorisierung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="4ee6a-140">Damit dies funktioniert müssen Sie diese Typen implementieren:</span><span class="sxs-lookup"><span data-stu-id="4ee6a-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="4ee6a-141">Ein Anforderungstyp, die IAuthorizationRequirement abgeleitet und enthält Felder, die die Details der Anforderung angegeben.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="4ee6a-142">Im Beispiel ist dies ein Altersfeld für den Typ der Beispiel-MinimumAgeRequirement.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="4ee6a-143">Ein Handler, der implementiert AuthorizationHandler&lt;T&gt;, wobei T der Typ des IAuthorizationRequirement ist, die der Ereignishandler erfüllen kann.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="4ee6a-144">Der Handler muss die Methode HandleRequirementAsync implementieren, die überprüft, ob die Anforderung erfüllt, die ein angegebenen Kontext, der Informationen über den Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="4ee6a-145">Wenn der Benutzer die Anforderung, die einen Aufruf von Kontext erfüllt werden. Wird erfolgreich anzugeben, dass der Benutzer autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="4ee6a-146">Wenn es mehrere Möglichkeiten gibt, dass ein Benutzer eine autorisierungsanforderung erfüllen möglicherweise mehrere Handler erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="4ee6a-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="4ee6a-147">Zusätzlich zum Registrieren von Anforderungen der benutzerdefinierten Richtlinie mit AddPolicy aufrufen, müssen Sie auch zum Registrieren des benutzerdefinierten Anforderung Handler über Abhängigkeiteneinschleusung (Services. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="4ee6a-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="4ee6a-148">Ein Beispiel eines benutzerdefinierten Autorisierungs-Anforderung und die Ereignishandler für die Überprüfung des Benutzers Age (auf der Grundlage eines Anspruchs DateOfBirth) ist verfügbar in der ASP.NET Core [Autorisierung Dokumentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="4ee6a-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ee6a-149">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4ee6a-149">Additional resources</span></span>

-   <span data-ttu-id="4ee6a-150">**ASP.NET Core Authentifizierung**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="4ee6a-151">**ASP.NET Core Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="4ee6a-152">**Rollenbasierte Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="4ee6a-153">**Benutzerdefinierte Richtlinie basierende Autorisierung**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="4ee6a-154">[Vorherigen] (index.md) [weiter] (Developer-app-Kennwörter-storage.md)</span><span class="sxs-lookup"><span data-stu-id="4ee6a-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
