---
title: Sichern von .NET-Microservices und Webanwendungen
description: ".NET Microservices-Architektur für .NET-Containeranwendungen | Sichern von .NET-Microservices und Webanwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 147aa099e440f5e5eb1dd6450946274aef91033a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="475b2-104">Sichern von .NET-Microservices und Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="475b2-104">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="475b2-105">Für Ressourcen und APIs, die durch einen Dienst verfügbar gemacht wurden, ist es oft notwendig, dass diese auf bestimmte vertrauenswürdige Benutzer oder Clients beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-105">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="475b2-106">Der erste Schritt zur Durchführung dieser Entscheidungen über die Vertrauenswürdigkeit auf API-Ebene ist die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="475b2-106">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="475b2-107">Die Authentifizierung ist der Prozess, um die Identität eines Benutzers sicher zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="475b2-107">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="475b2-108">In Microservice-Szenarios wird die Authentifizierung in der Regel zentral verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="475b2-108">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="475b2-109">Wenn Sie ein API-Gateway verwenden, ist dieses Gateway ein guter Ort, um die Authentifizierung durchzuführen, so wie in Abbildung 11-1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="475b2-109">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="475b2-110">Wenn Sie nach diesem Ansatz vorgehen, stellen Sie sicher, dass die einzelnen Microservices nicht direkt (ohne das API-Gateway) erreicht werden können, außer es kann zusätzliche Sicherheit garantiert werden, um Benachrichtigen danach zu authentifizieren, ob sie vom Gateway stammen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="475b2-110">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="475b2-111">**Abbildung 11-1**.</span><span class="sxs-lookup"><span data-stu-id="475b2-111">**Figure 11-1**.</span></span> <span data-ttu-id="475b2-112">Zentrale Authentifizierung mit einem API-Gateway</span><span class="sxs-lookup"><span data-stu-id="475b2-112">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="475b2-113">Wenn auf Dienste direkt zugegriffen werden kann, kann ein Authentifizierungsdienst wie Azure Active Directory oder ein dedizierter Authentifizierungs-Microservice, der als Sicherheitstokendienst (STS) fungiert, zum Authentifizieren von Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-113">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="475b2-114">Entscheidungen über die Vertrauenswürdigkeit werden zwischen Diensten mit Sicherheitstoken oder Cookies freigegeben.</span><span class="sxs-lookup"><span data-stu-id="475b2-114">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="475b2-115">(Diese können bei Bedarf zwischen Anwendungen in ASP.NET Core mit [Datenschutzdiensten](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications) freigegeben werden.) Dieses Muster ist in Abbildung 11-2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="475b2-115">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="475b2-116">**Abbildung 11-2**.</span><span class="sxs-lookup"><span data-stu-id="475b2-116">**Figure 11-2**.</span></span> <span data-ttu-id="475b2-117">Authentifizierung durch Identitäts-Microservice; das Vertrauen ist mithilfe eines Autorisierungstokens freigegeben.</span><span class="sxs-lookup"><span data-stu-id="475b2-117">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="475b2-118">Authentifizierung mit ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="475b2-118">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="475b2-119">Der primäre Mechanismus in ASP.NET Core zur Identifizierung eines Anwendungsbenutzers ist das Mitgliedschaftssystem [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="475b2-119">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="475b2-120">ASP.NET Core Identity speichert Benutzerinformationen (einschließlich Anmeldeinformationen, Rollen und Ansprüche) in einem Datenspeicher, der vom Entwickler konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="475b2-120">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="475b2-121">Normalerweise ist der ASP.NET Core Identity-Datenspeicher ein Entity Framework-Speicher, der im Microsoft.AspNetCore.Identity.EntityFrameworkCore-Paket bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="475b2-121">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="475b2-122">Jedoch können benutzerdefinierte Speicher oder andere Pakete von Drittanbietern zum Speichern von Identitätsinformationen in Azure Table Storage, DocumentDB oder anderen Speicherorten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-122">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="475b2-123">Der folgende Code wird aus der Projektvorlage der ASP.NET Core-Webanwendung genommen, für die eine einzelne Benutzerkontoauthentifizierung ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="475b2-123">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="475b2-124">Er stellt dar, wie ASP.NET Core Identiy mithilfe von EntityFramework.Core in der Startup.ConfigureServices-Methode konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="475b2-124">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="475b2-125">Sobald ASP.NET Core Identity konfiguriert ist, aktivieren Sie den Dienst, indem Sie „app.UseIdentity“ in der Startup.Configure-Methode des Diensts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="475b2-125">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="475b2-126">Durch die Verwendung von ASP.NET Code Identity sind mehrere Szenarios möglich:</span><span class="sxs-lookup"><span data-stu-id="475b2-126">Using ASP.NET Code Identity enables several scenarios:</span></span>

-   <span data-ttu-id="475b2-127">Erstellen Sie neue Benutzerinformationen mithilfe des UserManager-Typs (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="475b2-127">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="475b2-128">Authentifizieren Sie Benutzer mithilfe des SignInManager-Typs.</span><span class="sxs-lookup"><span data-stu-id="475b2-128">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="475b2-129">Sie können „signInManager.SignInAsync“ verwenden, um sich direkt anzumelden, oder „signInManager.PasswordSignInAsync“, um zu bestätigen, dass das Kennwort des Benutzers korrekt ist, und um diesen anschließend anzumelden.</span><span class="sxs-lookup"><span data-stu-id="475b2-129">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="475b2-130">Identifizieren Sie einen Benutzer auf Grundlage von Informationen, die in einem Cookie gespeichert sind (das von der ASP.NET Core Identity-Middleware gelesen wird), damit nachfolgende Anforderungen von einem Browser die Identität und Ansprüche eines angemeldeten Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="475b2-130">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="475b2-131">ASP.NET Core Identity unterstützt auch die [zweistufige Authentifizierung](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="475b2-131">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="475b2-132">ASP.NET Core Identity ist eine empfohlene Lösung für Authentifizierungsszenarios, die einen Datenspeicher für lokale Benutzerdaten verwenden und die Identität zwischen Anforderungen mithilfe von Cookies (was typisch für MVC-Webanwendungen ist) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="475b2-132">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="475b2-133">Authentifizierung mithilfe externer Anbieter</span><span class="sxs-lookup"><span data-stu-id="475b2-133">Authenticating using external providers</span></span>

<span data-ttu-id="475b2-134">ASP.NET Core unterstützt auch die Verwendung von [externen Authentifizierungsanbietern](https://docs.microsoft.com/aspnet/core/security/authentication/social/), damit sich Benutzer über [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)-Flows anmelden können.</span><span class="sxs-lookup"><span data-stu-id="475b2-134">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="475b2-135">Das bedeutet, dass sich Benutzer mithilfe von vorhandenen Authentifizierungsprozessen von Anbietern wie Microsoft, Google, Facebook oder Twitter anmelden können und diese Identitäten ASP.NET Core Identity in Ihrer Anwendung zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="475b2-135">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="475b2-136">Für die Verwendung der externen Authentifizierung schließen Sie die entsprechende Authentifizierungsmiddleware in der HTTP-Pipeline zum Verarbeiten von Anforderungen ein.</span><span class="sxs-lookup"><span data-stu-id="475b2-136">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="475b2-137">Diese Middleware ist für die Verarbeitung von Anforderungen verantwortlich, um URI-Routen vom Authentifizierungsanbieter zurückzugeben, um Identitätsinformationen zu erfassen und diese über die SignInManager.GetExternalLoginInfo-Methode verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="475b2-137">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="475b2-138">Beliebte externe Authentifizierungsanbieter sowie deren zugeordnete NuGet-Pakete sind unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="475b2-138">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="475b2-139">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="475b2-139">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="475b2-140">**Google:** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="475b2-140">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="475b2-141">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="475b2-141">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="475b2-142">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="475b2-142">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="475b2-143">In jedem Fall wird die Middleware mit einem Aufruf auf eine Registrierungsmethode registriert. Dieser Aufruf ähnelt app.Use{ExternalProvider}Authentication in Startup.Configure.</span><span class="sxs-lookup"><span data-stu-id="475b2-143">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="475b2-144">Diese Registrierungsmethoden nehmen ein Options-Objekt, das je nach Anbieter eine Anwendungs-ID sowie geheime Informationen (beispielsweise ein Kennwort) enthält.</span><span class="sxs-lookup"><span data-stu-id="475b2-144">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="475b2-145">Externe Authentifizierungsanbieter erfordern, dass die Anwendung registriert ist (so wie in der [ASP.NET Core-Dokumentation beschrieben](https://docs.microsoft.com/aspnet/core/security/authentication/social/)), sodass sie den Benutzer darüber informieren können, welche Anwendung Zugriff auf ihre Identität anfordert.</span><span class="sxs-lookup"><span data-stu-id="475b2-145">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="475b2-146">Sobald die Middleware in Startup.Configure registriert ist, können Sie Benutzer auffordern, sich von einer beliebigen Controlleraktion aus anzumelden.</span><span class="sxs-lookup"><span data-stu-id="475b2-146">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="475b2-147">Um dies zu ermöglichen, erstellen Sie ein AuthenticationProperties-Objekt, das den Namen und die Umleitungs-URL des Authentifizierungsanbieters enthält.</span><span class="sxs-lookup"><span data-stu-id="475b2-147">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="475b2-148">Sie geben anschließend eine „Challenge“-Antwort zurück, die das AuthenticationProperties-Objekt übergibt.</span><span class="sxs-lookup"><span data-stu-id="475b2-148">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="475b2-149">Im folgenden Code ist ein Beispiel dafür dargestellt.</span><span class="sxs-lookup"><span data-stu-id="475b2-149">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="475b2-150">Der redirectUrl-Parameter enthält die URL, auf die der externe Anbieter umleiten soll, sobald sich der Benutzer authentifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="475b2-150">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="475b2-151">Die URL sollte eine Aktion darstellen, die den Benutzer, wie im folgenden vereinfachten Beispiel dargestellt, auf Grundlage externer Identitätsinformationen anmelden soll:</span><span class="sxs-lookup"><span data-stu-id="475b2-151">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

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

<span data-ttu-id="475b2-152">Wenn Sie die Authentifizierungsoption **Individual User Account** (Einzelbenutzerkonto) auswählen, wenn Sie das ASP.NET Code-Webanwendungsprojekt in Visual Studio erstellen, befindet sich der Code, der zur Anmeldung mit einem externen Anbieter benötigt wird, bereits im Projekt. Dies ist in Abbildung 11-3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="475b2-152">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="475b2-154">**Abbildung 11-3**.</span><span class="sxs-lookup"><span data-stu-id="475b2-154">**Figure 11-3**.</span></span> <span data-ttu-id="475b2-155">Auswählen einer Option zur Verwendung der externen Authentifizierung beim Erstellen eines Webanwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="475b2-155">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="475b2-156">Zusätzlich zu den zuvor aufgeführten externen Authentifizierungsanbietern sind Pakete Dritter verfügbar, die Middleware zur Verwendung mehrerer externer Authentifizierungsanbieter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="475b2-156">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="475b2-157">Eine Liste finden Sie im [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="475b2-157">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="475b2-158">Es ist natürlich auch möglich, Ihre eigene Middleware für die externe Authentifizierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="475b2-158">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="475b2-159">Authentifizierung mit Bearertoken</span><span class="sxs-lookup"><span data-stu-id="475b2-159">Authenticating with bearer tokens</span></span>

<span data-ttu-id="475b2-160">Die Authentifizierung mit ASP.NET Core Identity (oder Identity plus externer Authentifizierunsanbieter) funktioniert für viele Webanwendungsszenarios einwandfrei, für die das Speichern von Benutzerinformationen in einem Cookie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="475b2-160">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="475b2-161">In anderen Szenarios sind Cookies jedoch kein natürlicher Vorgang zum Beibehalten und Übertragen von Daten.</span><span class="sxs-lookup"><span data-stu-id="475b2-161">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="475b2-162">Beispielsweise verwenden Sie in einer ASP.NET Core-Web-API, die RESTful-Endpunkte verfügbar macht, auf die möglicherweise Einzelseitenanwendungen, native Clients oder auch andere Web-APIs zugreifen, stattdessen Bearertoken.</span><span class="sxs-lookup"><span data-stu-id="475b2-162">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="475b2-163">Diese Anwendungstypen funktionieren nicht mit Cookies, können jedoch einfach ein Bearertoken abrufen und dieses in den Autorisierungsheader nachfolgender Anforderungen einfügen.</span><span class="sxs-lookup"><span data-stu-id="475b2-163">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="475b2-164">Für die Tokenauthentifizierung unterstützt ASP.NET Core mehrere Optionen zur Verwendung von [OAuth 2.0](https://oauth.net/2/) und [OpenID Connect](http://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="475b2-164">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](http://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="475b2-165">Authentifizierung mit einem OpenID Connect- und OAuth 2.0-Identitätsanbieter</span><span class="sxs-lookup"><span data-stu-id="475b2-165">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="475b2-166">Wenn Benutzerinformationen in Azure Active Directory oder einer anderen Identitätslösung gespeichert werden, die OpenID Connect oder OAuth 2.0 verwendet, können Sie das Paket „Microsoft.AspNetCore.Authentication.OpenIdConnect“ für die Authentifizierung mithilfe des OpenID Connect-Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="475b2-166">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="475b2-167">Um sich z.B. [für Azure Active Directory zu authentifizieren](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), kann eine ASP.NET Core-Webanwendung, wie in folgendem Beispiel gezeigt, Middleware aus diesem Paket verwenden:</span><span class="sxs-lookup"><span data-stu-id="475b2-167">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

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

<span data-ttu-id="475b2-168">Die Konfigurationswerte sind Azure Active Directory-Werte, die erstellt werden, wenn Ihre Anwendung [als Azure AD-Client registriert ist](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="475b2-168">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="475b2-169">Eine einzelne Client-ID kann zwischen mehreren Microservices in einer Anwendung freigegeben werden, wenn sie alle Benutzer authentifizieren müssen, die über Azure Active Directory authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-169">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="475b2-170">Beachten Sie, dass wenn Sie diesen Workflow verwenden, die ASP.NET Core Identity-Middleware nicht erforderlich ist, da der gesamte Speicher und die Authentifizierung der Benutzerinformationen von Azure Active Directory behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-170">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="475b2-171">Ausstellen von Sicherheitstoken von einem ASP.NET Core-Dienst</span><span class="sxs-lookup"><span data-stu-id="475b2-171">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="475b2-172">Wenn Sie lieber Sicherheitstoken für lokale ASP.NET Core Identity-Benutzer ausstellen möchten, anstatt einen externen Identitätsanbieter zu verwenden, können Sie von einigen guten Bibliotheken von Drittanbietern profitieren.</span><span class="sxs-lookup"><span data-stu-id="475b2-172">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="475b2-173">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) und [OpenIddict](https://github.com/openiddict/openiddict-core) sind OpenID Connect-Anbieter, die sich einfach in ASP.NET Core Identity integrieren lassen, damit Sie Sicherheitstoken von einem ASP.NET Core-Dienst ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="475b2-173">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="475b2-174">Die [IdentityServer4-Dokumentation](https://identityserver4.readthedocs.io/en/release/) bietet detaillierte Anweisungen zur Verwendung der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="475b2-174">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="475b2-175">Jedoch sind die grundlegenden Schritte zur Verwendung von IdentityServer4 zur Ausstellung von Token wie folgt.</span><span class="sxs-lookup"><span data-stu-id="475b2-175">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="475b2-176">Sie können UseIdentityServer in der Startup.Configure-Methode aufrufen, um IdentityServer4 der HTTP_Anforderungsverarbeitungspipeline hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="475b2-176">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="475b2-177">Dadurch kann die Bibliothek Anforderungen an OpenID Connect und OAuth2-Endpunkte wie „/connect/token“ verarbeiten</span><span class="sxs-lookup"><span data-stu-id="475b2-177">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="475b2-178">Sie konfigurieren IdentityServer4 in Startup.ConfigureServices, indem Sie services.AddIdentityServer aufrufen.</span><span class="sxs-lookup"><span data-stu-id="475b2-178">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="475b2-179">Sie konfigurieren Identitätsserver, indem Sie folgende Daten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="475b2-179">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="475b2-180">Die zu verwendenden [Anmeldeinformationen](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="475b2-180">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="475b2-181">Die [Identitäts- und API-Ressourcen](https://identityserver4.readthedocs.io/en/release/topics/resources.html), auf die Benutzer möglicherweise Zugriff anfordern:</span><span class="sxs-lookup"><span data-stu-id="475b2-181">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="475b2-182">API-Ressourcen stellen geschützte Daten oder Funktionen dar, auf die ein Benutzer mit einem Zugriffstoken zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="475b2-182">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="475b2-183">Ein Beispiel einer API-Ressource wäre eine Web-API (oder ein Satz von APIs), für die die Autorisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="475b2-183">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="475b2-184">Identitätsressourcen stellen Informationen (Ansprüche) dar, die einem Client zur Identifizierung eines Benutzers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-184">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="475b2-185">Die Ansprüche können den Benutzernamen, die E-Mail-Adresse usw. beinhalten.</span><span class="sxs-lookup"><span data-stu-id="475b2-185">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="475b2-186">Die [Clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html), die eine Verbindung herstellen, um Token anzufordern.</span><span class="sxs-lookup"><span data-stu-id="475b2-186">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="475b2-187">Der Speichermechanismus für Benutzerinformationen, z.B. [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) oder eine Alternative.</span><span class="sxs-lookup"><span data-stu-id="475b2-187">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="475b2-188">Wenn Sie Clients und Ressourcen angeben, die IdentityServer4 verwenden sollen, können Sie eine IEnumerable&lt;T&gt;-Auflistung der geeigneten Typen an Methoden übergeben, die einen In-Memory-Client oder Ressourcenspeicher übernehmen.</span><span class="sxs-lookup"><span data-stu-id="475b2-188">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="475b2-189">Für komplexere Szenarios können Sie auch Client- oder Ressourcenanbietertypen über eine Abhängigkeitsinjektion nutzen.</span><span class="sxs-lookup"><span data-stu-id="475b2-189">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="475b2-190">Eine Beispielkonfiguration für IdentityServer4 zur Verwendung von In-Memory-Ressourcen und -Clients, die von einem benutzerdefinierten IClientStore-Typen bereitgestellt werden, könnten wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="475b2-190">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="475b2-191">Nutzen von Sicherheitstoken</span><span class="sxs-lookup"><span data-stu-id="475b2-191">Consuming security tokens</span></span>

<span data-ttu-id="475b2-192">Die Authentifizierung bei einem OpenID Connect-Endpunkt oder die Ausstellung Ihrer eigenen Sicherheitstoken deckt einige Szenarios ab.</span><span class="sxs-lookup"><span data-stu-id="475b2-192">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="475b2-193">Was ist jedoch mit dem Dienst, der einfach nur den Zugriff für jene Benutzer einschränken muss, die über gültige Sicherheitstoken verfügen, die von einem anderen Dienst bereitgestellt wurden?</span><span class="sxs-lookup"><span data-stu-id="475b2-193">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="475b2-194">Für dieses Szenario ist die Middleware zur Authentifizierung, die JWT-Token behandelt, im Microsoft.AspNetCore.Authentication.JwtBearer-Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="475b2-194">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="475b2-195">JWT steht für „[JSON Web Token](https://tools.ietf.org/html/rfc7519)“ und ist ein allgemeines Sicherheitstokenformat (definiert von RFC 7519) zum Kommunizieren von Sicherheitsansprüchen.</span><span class="sxs-lookup"><span data-stu-id="475b2-195">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="475b2-196">Ein einfaches Beispiel zur Verwendung von Middleware, um Token wie diese zu nutzen, sieht möglicherweise wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="475b2-196">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="475b2-197">Dieser Code muss vor Aufrufen auf die ASP.NET Core-MVC-Middleware (app.UseMvc) stehen.</span><span class="sxs-lookup"><span data-stu-id="475b2-197">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="475b2-198">Die Parameter hier sind:</span><span class="sxs-lookup"><span data-stu-id="475b2-198">The parameters in this usage are:</span></span>

-   <span data-ttu-id="475b2-199">„Audience“ stellt den Empfänger des eingehenden Tokens oder der Ressource dar, für die das Token den Zugriff erteilt.</span><span class="sxs-lookup"><span data-stu-id="475b2-199">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="475b2-200">Wenn der in diesem Wert angegebene Parameter nicht mit dem aud-Parameter im Token übereinstimmt, wird das Token abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="475b2-200">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="475b2-201">„Authority“ ist die Adresse des Authentifizierungsservers, der Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="475b2-201">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="475b2-202">Die Middleware zur JWT-Bearerauthentifizierung verwendet diesen URI, um den öffentlichen Schlüssel abzurufen, der zur Überprüfung der Tokensignatur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="475b2-202">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="475b2-203">Die Middleware bestätigt auch, dass der iss-Parameter im Token mit diesem URI übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="475b2-203">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="475b2-204">„AutomaticAuthenticate“ ist ein boolescher Wert, der angibt, ob der vom Token definierte Benutzer automatisch angemeldet werden soll.</span><span class="sxs-lookup"><span data-stu-id="475b2-204">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="475b2-205">Ein weiterer Parameter, „RequireHttpsMetadata“, wird in diesem Beispiel nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="475b2-205">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="475b2-206">Er ist nützlich zu Testzwecken; Sie legen diesen Parameter auf FALSE fest, damit Sie Tests in Umgebungen durchführen können, in denen Sie keine Zertifikate verfügen.</span><span class="sxs-lookup"><span data-stu-id="475b2-206">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="475b2-207">In realen Bereitstellungen dürfen JWT-Bearertoken immer nur über HTTPS übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="475b2-207">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="475b2-208">Wenn diese Middleware vorhanden ist, werden JWT-Token automatisch aus Autorisierungsheadern extrahiert.</span><span class="sxs-lookup"><span data-stu-id="475b2-208">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="475b2-209">Sie werden anschließend deserialisiert, überprüft (mithilfe der Werte in den Parametern „Audience“ und „Authority“) und als Benutzerinformation gespeichert, auf die später durch MVC-Aktionen oder Autorisierungsfilter verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="475b2-209">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="475b2-210">Die Middleware für die JWT-Bearerauthentifizierung kann auch erweiterte Szenarios unterstützen, beispielsweise die Verwendung eines lokalen Zertifikats zur Überprüfung eines Tokens, wenn die Registrierungsstelle nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="475b2-210">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="475b2-211">Für dieses Szenario können Sie ein TokenValidationParameters-Objekt im JwtBearerOptions-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="475b2-211">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="475b2-212">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="475b2-212">Additional resources</span></span>

-   <span data-ttu-id="475b2-213">**Sharing cookies between applications (Freigeben von Cookies zwischen Anwendungen)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="475b2-213">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="475b2-214">**Introduction to Identity (Einführung in Identity)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="475b2-214">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="475b2-215">**Rick Anderson. Two-factor authentication with SMS (Zweistufige Authentifizierung mit SMS)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="475b2-215">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="475b2-216">**Enabling authentication using Facebook, Google and other external providers (Zulassen der Authentifizierung mit Facebook, Google und anderen externen Anbietern)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="475b2-216">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="475b2-217">**Michell Anicas. An Introduction to OAuth 2 (Eine Einführung in OAuth 2)**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span><span class="sxs-lookup"><span data-stu-id="475b2-217">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="475b2-218">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span><span class="sxs-lookup"><span data-stu-id="475b2-218">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [<span data-ttu-id="475b2-219">*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*</span><span class="sxs-lookup"><span data-stu-id="475b2-219">*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*</span></span>](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="475b2-220">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app (Integrieren von Azure AD in die ASP.NET Core-Web-App)**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span><span class="sxs-lookup"><span data-stu-id="475b2-220">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="475b2-221">**IdentityServer4. Official documentation (Offizielle Dokumentation zu IdentityServer4)**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="475b2-221">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="475b2-222">[Zurück] (../implement-resilient-applications/monitor-app-health.md) [Weiter] (authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="475b2-222">[Previous] (../implement-resilient-applications/monitor-app-health.md) [Next] (authorization-net-microservices-web-applications.md)</span></span>
