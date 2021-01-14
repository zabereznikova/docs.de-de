---
title: Sichern von .NET-Microservices und Webanwendungen
description: Sicherheit in .NET-Microservices und -Webanwendungen – Lernen Sie die Authentifizierungsoptionen in ASP.NET Core-Webanwendungen kennen.
author: mjrousos
ms.date: 01/13/2021
ms.openlocfilehash: 1bb03e8abdf6daa0b6c4570eb35643898f797cc0
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188046"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="01394-103">Erstellen sicherer .NET-Microservices und -Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="01394-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="01394-104">Das Thema Sicherheit in Microservices und Webanwendung umfasst so viele Aspekte, dass sich damit problemlos mehrere Bücher füllen lassen – so wie dieses.</span><span class="sxs-lookup"><span data-stu-id="01394-104">There are so many aspects about security in microservices and web applications that the topic could easily take several books like this one.</span></span> <span data-ttu-id="01394-105">In diesem Abschnitt beschäftigen wir uns mit den Aspekten Authentifizierung, Autorisierung und Anwendungsgeheimnisse.</span><span class="sxs-lookup"><span data-stu-id="01394-105">So, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="01394-106">Implementieren von Authentifizierung in .NET-Microservices und -Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="01394-106">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="01394-107">Ressourcen und APIs, die durch einen Dienst veröffentlicht wurden, müssen oftmals auf bestimmte vertrauenswürdige Benutzer oder Clients beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="01394-107">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="01394-108">Der erste Schritt zur Durchführung dieser Entscheidungen über die Vertrauenswürdigkeit auf API-Ebene ist die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="01394-108">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="01394-109">Authentifizierung bezeichnet den Vorgang, die Identität eines Benutzers zuverlässig zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="01394-109">Authentication is the process of reliably verifying a user's identity.</span></span>

<span data-ttu-id="01394-110">In Microservice-Szenarios wird die Authentifizierung in der Regel zentral verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="01394-110">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="01394-111">Wenn Sie ein API-Gateway verwenden, ist dieses Gateway ein guter Ort, um die Authentifizierung durchzuführen, so wie in Abbildung 9-1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="01394-111">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="01394-112">Wenn Sie nach diesem Ansatz vorgehen, stellen Sie sicher, dass die einzelnen Microservices nicht direkt (ohne das API-Gateway) erreicht werden können, außer es kann zusätzliche Sicherheit garantiert werden, um Benachrichtigen danach zu authentifizieren, ob sie vom Gateway stammen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="01394-112">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Das folgenden Diagramm zeigt, wie die mobile Client-App mit dem Back-End interagiert.](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="01394-114">**Abbildung 9-1**.</span><span class="sxs-lookup"><span data-stu-id="01394-114">**Figure 9-1**.</span></span> <span data-ttu-id="01394-115">Zentrale Authentifizierung mit einem API-Gateway</span><span class="sxs-lookup"><span data-stu-id="01394-115">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="01394-116">Wenn die Authentifizierung im API-Gateway zentralisiert ist, fügt dieses Anforderungen beim Weiterleiten an die Microservices Benutzerinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="01394-116">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="01394-117">Wenn auf Dienste direkt zugegriffen werden kann, kann ein Authentifizierungsdienst wie Azure Active Directory oder ein dedizierter Authentifizierungs-Microservice, der als Sicherheitstokendienst (STS) fungiert, zum Authentifizieren von Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01394-117">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="01394-118">Entscheidungen über die Vertrauenswürdigkeit werden zwischen Diensten mit Sicherheitstoken oder Cookies freigegeben.</span><span class="sxs-lookup"><span data-stu-id="01394-118">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="01394-119">(Diese Token können bei Bedarf zwischen ASP.NET Core-Anwendungen durch Implementierung der [gemeinsamen Nutzung von Cookies](/aspnet/core/security/cookie-sharing) freigegeben werden.) Dieses Muster ist in Abbildung 9-2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="01394-119">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![Das folgende Diagramm zeigt die Authentifizierung durch Back-End-Microservices.](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="01394-121">**Abbildung 9-2:**</span><span class="sxs-lookup"><span data-stu-id="01394-121">**Figure 9-2**.</span></span> <span data-ttu-id="01394-122">Authentifizierung durch Identitäts-Microservice; das Vertrauen ist mithilfe eines Autorisierungstokens freigegeben.</span><span class="sxs-lookup"><span data-stu-id="01394-122">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="01394-123">Beim direkten Zugriff auf Microservices wird die Vertrauensstellung, die Authentifizierung und Autorisierung beinhaltet, mithilfe eines Sicherheitstokens behandelt, das von einem von den Microservices gemeinsam verwendeten, dedizierten Microservice herausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="01394-123">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="01394-124">Authentifizierung mit ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="01394-124">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="01394-125">Der primäre Mechanismus in ASP.NET Core zur Identifizierung eines Anwendungsbenutzers ist das Mitgliedschaftssystem [ASP.NET Core Identity](/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="01394-125">The primary mechanism in ASP.NET Core for identifying an application's users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="01394-126">ASP.NET Core Identity speichert Benutzerinformationen (einschließlich Anmeldeinformationen, Rollen und Ansprüche) in einem Datenspeicher, der vom Entwickler konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="01394-126">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="01394-127">Normalerweise ist der ASP.NET Core Identity-Datenspeicher ein Entity Framework-Speicher, der im `Microsoft.AspNetCore.Identity.EntityFrameworkCore`-Paket bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="01394-127">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="01394-128">Jedoch können benutzerdefinierte Speicher oder andere Pakete von Drittanbietern zum Speichern von Identitätsinformationen in Azure Table Storage, CosmosDB oder anderen Speicherorten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01394-128">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

> [!TIP]
> <span data-ttu-id="01394-129">ASP.NET Core 2.1 und höher stellt [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) als [Razor-Klassenbibliothek](/aspnet/core/razor-pages/ui-class) bereit, sodass Sie in Ihrem Projekt nicht viel vom notwendigen Code sehen werden, so wie es in den vorherigen Versionen der Fall war.</span><span class="sxs-lookup"><span data-stu-id="01394-129">ASP.NET Core 2.1 and later provides [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) as a [Razor Class Library](/aspnet/core/razor-pages/ui-class), so you won't see much of the necessary code in your project, as was the case for previous versions.</span></span> <span data-ttu-id="01394-130">Ausführliche Informationen zum Anpassen des Codes für Identity an Ihre Anforderungen finden Sie unter [Erstellen eines Identity-Gerüsts in ASP.NET Core-Projekten](/aspnet/core/security/authentication/scaffold-identity).</span><span class="sxs-lookup"><span data-stu-id="01394-130">For details on how to customize the Identity code to suit your needs, see [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity).</span></span>

<span data-ttu-id="01394-131">Der folgende Code entstammt der Projektvorlage „ASP.NET Core Web Application MVC 3.1“, für die die Authentifizierung mit einem einzelnen Benutzerkonto ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="01394-131">The following code is taken from the ASP.NET Core Web Application MVC 3.1 project template with individual user account authentication selected.</span></span> <span data-ttu-id="01394-132">Der Code veranschaulicht, wie Sie ASP.NET Core Identity mithilfe von Entity Framework Core in der `Startup.ConfigureServices`-Methode konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01394-132">It shows how to configure ASP.NET Core Identity using Entity Framework Core in the `Startup.ConfigureServices` method.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
    //...
}
```

<span data-ttu-id="01394-133">Wenn ASP.NET Core Identity konfiguriert ist, erfolgt die Aktivierung, indem Sie `app.UseAuthentication()` und `endpoints.MapRazorPages()` der `Startup.Configure`-Methode des Diensts hinzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="01394-133">Once ASP.NET Core Identity is configured, you enable it by adding the `app.UseAuthentication()` and `endpoints.MapRazorPages()` as shown in the following code in the service's `Startup.Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    //...
    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
    //...
}
```

> [!IMPORTANT]
> <span data-ttu-id="01394-134">Die Zeilen im obigen Code **MÜSSEN DIE GEZEIGTE REIHENFOLGE AUFWEISEN**, damit Identity ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="01394-134">The lines in the preceding code **MUST BE IN THE ORDER SHOWN** for Identity to work correctly.</span></span>

<span data-ttu-id="01394-135">Durch die Verwendung von ASP.NET Core Identity sind mehrere Szenarios möglich:</span><span class="sxs-lookup"><span data-stu-id="01394-135">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="01394-136">Erstellen Sie neue Benutzerinformationen mithilfe des UserManager-Typs (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="01394-136">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="01394-137">Authentifizieren Sie Benutzer mithilfe des SignInManager-Typs.</span><span class="sxs-lookup"><span data-stu-id="01394-137">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="01394-138">Sie können `signInManager.SignInAsync` für die direkte Anmeldung verwenden oder mithilfe von `signInManager.PasswordSignInAsync` die Richtigkeit des Benutzerkennworts bestätigen und diesen anschließend anmelden.</span><span class="sxs-lookup"><span data-stu-id="01394-138">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user's password is correct and then sign them in.</span></span>

- <span data-ttu-id="01394-139">Identifizieren Sie einen Benutzer auf Grundlage von Informationen, die in einem Cookie gespeichert sind (das von der ASP.NET Core Identity-Middleware gelesen wird), damit nachfolgende Anforderungen von einem Browser die Identität und Ansprüche eines angemeldeten Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="01394-139">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user's identity and claims.</span></span>

<span data-ttu-id="01394-140">ASP.NET Core Identity unterstützt auch die [zweistufige Authentifizierung](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="01394-140">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="01394-141">ASP.NET Core Identity ist eine empfohlene Lösung für Authentifizierungsszenarios, die einen Datenspeicher für lokale Benutzerdaten verwenden und die Identität zwischen Anforderungen mithilfe von Cookies (was typisch für MVC-Webanwendungen ist) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="01394-141">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="01394-142">Authentifizierung mithilfe externer Anbieter</span><span class="sxs-lookup"><span data-stu-id="01394-142">Authenticate with external providers</span></span>

<span data-ttu-id="01394-143">ASP.NET Core unterstützt auch die Verwendung von [externen Authentifizierungsanbietern](/aspnet/core/security/authentication/social/), damit sich Benutzer über [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)-Flows anmelden können.</span><span class="sxs-lookup"><span data-stu-id="01394-143">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="01394-144">Das bedeutet, dass sich Benutzer mithilfe von vorhandenen Authentifizierungsprozessen von Anbietern wie Microsoft, Google, Facebook oder Twitter anmelden können und diese Identitäten ASP.NET Core Identity in Ihrer Anwendung zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="01394-144">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="01394-145">Um eine externe Authentifizierung zu verwenden, müssen Sie zum einen, wie bereits erwähnt, mithilfe der `app.UseAuthentication()`-Methode die Authentifizierungsmiddleware einschließen. Zum anderen müssen Sie den externen Anbieter in `Startup` registrieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="01394-145">To use external authentication, besides including the authentication middleware as mentioned before, using the `app.UseAuthentication()` method, you also have to register the external provider in `Startup` as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddAuthentication()
        .AddMicrosoftAccount(microsoftOptions =>
        {
            microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ClientId"];
            microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:ClientSecret"];
        })
        .AddGoogle(googleOptions => { ... })
        .AddTwitter(twitterOptions => { ... })
        .AddFacebook(facebookOptions => { ... });
    //...
}
```

<span data-ttu-id="01394-146">Beliebte externe Authentifizierungsanbieter sowie deren zugeordnete NuGet-Pakete sind in der folgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="01394-146">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="01394-147">**Anbieter**</span><span class="sxs-lookup"><span data-stu-id="01394-147">**Provider**</span></span>  | <span data-ttu-id="01394-148">**Pakete**</span><span class="sxs-lookup"><span data-stu-id="01394-148">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="01394-149">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="01394-149">**Microsoft**</span></span> | <span data-ttu-id="01394-150">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="01394-150">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="01394-151">**Google**</span><span class="sxs-lookup"><span data-stu-id="01394-151">**Google**</span></span>    | <span data-ttu-id="01394-152">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="01394-152">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="01394-153">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="01394-153">**Facebook**</span></span>  | <span data-ttu-id="01394-154">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="01394-154">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="01394-155">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="01394-155">**Twitter**</span></span>   | <span data-ttu-id="01394-156">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="01394-156">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="01394-157">In allen Fällen müssen Sie ein Verfahren zur Anwendungsregistrierung durchlaufen, das vom jeweiligen Anbieter abhängig ist und in der Regel folgende Schritte umfasst:</span><span class="sxs-lookup"><span data-stu-id="01394-157">In all cases, you must complete an application registration procedure that is vendor dependent and that usually involves:</span></span>

1. <span data-ttu-id="01394-158">Sie rufen eine Clientanwendungs-ID ab.</span><span class="sxs-lookup"><span data-stu-id="01394-158">Getting a Client Application ID.</span></span>
2. <span data-ttu-id="01394-159">Sie rufen einen Clientanwendungsserver ab.</span><span class="sxs-lookup"><span data-stu-id="01394-159">Getting a Client Application Secret.</span></span>
3. <span data-ttu-id="01394-160">Sie konfigurieren eine Umleitungs-URL, die von der Autorisierungsmiddleware und dem registrierten Anbieter verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="01394-160">Configuring an redirection URL, that's handled by the authorization middleware and the registered provider</span></span>
4. <span data-ttu-id="01394-161">Optional konfigurieren Sie eine Abmelde-URL, um Abmeldungen in einem SSO-Szenario (Single Sign-On, einmaliges Anmelden) ordnungsgemäß zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01394-161">Optionally, configuring a sign-out URL to properly handle sign out in a Single Sign On (SSO) scenario.</span></span>

<span data-ttu-id="01394-162">Ausführliche Informationen zum Konfigurieren Ihrer App für einen externen Anbieter finden Sie in der [ASP.NET Core-Dokumentation im Artikel zur Authentifizierung über externe Anbieter](/aspnet/core/security/authentication/social/).</span><span class="sxs-lookup"><span data-stu-id="01394-162">For details on configuring your app for an external provider, see the [External provider authentication in the ASP.NET Core documentation](/aspnet/core/security/authentication/social/)).</span></span>

>[!TIP]
><span data-ttu-id="01394-163">Alle Details werden von den bereits erwähnten Middlewarekomponenten und Diensten zur Autorisierung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="01394-163">All details are handled by the authorization middleware and services previously mentioned.</span></span> <span data-ttu-id="01394-164">Wenn Sie das ASP.NET Core-Webanwendungsprojekt in Visual Studio erstellen, müssen Sie also zusätzlich zur Registrierung der Authentifizierungsanbieter einfach nur die Authentifizierungsoption **Einzelne Benutzerkonten** auswählen, wie in Abbildung 9-3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="01394-164">So, you just have to choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, as shown in Figure 9-3, besides registering the authentication providers previously mentioned.</span></span>

![Screenshot des Dialogfelds „Neue ASP.NET Core-Webanwendung“](./media/index/select-individual-user-account-authentication-option.png)

<span data-ttu-id="01394-166">**Abbildung 9-3.**</span><span class="sxs-lookup"><span data-stu-id="01394-166">**Figure 9-3**.</span></span> <span data-ttu-id="01394-167">Auswählen der Option „Einzelne Benutzerkonten“ zur Verwendung der externen Authentifizierung beim Erstellen eines Webanwendungsprojekts in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="01394-167">Selecting the Individual User Accounts option, for using external authentication, when creating a web application project in Visual Studio 2019.</span></span>

<span data-ttu-id="01394-168">Zusätzlich zu den zuvor aufgeführten externen Authentifizierungsanbietern sind Pakete Dritter verfügbar, die Middleware zur Verwendung mehrerer externer Authentifizierungsanbieter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="01394-168">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="01394-169">Eine Liste finden Sie im [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)-Repository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="01394-169">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repository on GitHub.</span></span>

<span data-ttu-id="01394-170">Um besonderen Anforderungen gerecht zu werden, können Sie auch eigene Middleware zur externen Authentifizierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="01394-170">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="01394-171">Authentifizierung mit Bearertoken</span><span class="sxs-lookup"><span data-stu-id="01394-171">Authenticate with bearer tokens</span></span>

<span data-ttu-id="01394-172">Die Authentifizierung mit ASP.NET Core Identity (oder Identity plus externer Authentifizierunsanbieter) funktioniert für viele Webanwendungsszenarios einwandfrei, für die das Speichern von Benutzerinformationen in einem Cookie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="01394-172">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="01394-173">In anderen Szenarios sind Cookies jedoch kein natürlicher Vorgang zum Beibehalten und Übertragen von Daten.</span><span class="sxs-lookup"><span data-stu-id="01394-173">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="01394-174">Beispielsweise verwenden Sie in einer ASP.NET Core-Web-API, die RESTful-Endpunkte verfügbar macht, auf die möglicherweise Einzelseitenanwendungen, native Clients oder auch andere Web-APIs zugreifen, stattdessen Bearertoken.</span><span class="sxs-lookup"><span data-stu-id="01394-174">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="01394-175">Diese Anwendungstypen funktionieren nicht mit Cookies, können jedoch einfach ein Bearertoken abrufen und dieses in den Autorisierungsheader nachfolgender Anforderungen einfügen.</span><span class="sxs-lookup"><span data-stu-id="01394-175">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="01394-176">Für die Tokenauthentifizierung unterstützt ASP.NET Core mehrere Optionen zur Verwendung von [OAuth 2.0](https://oauth.net/2/) und [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="01394-176">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="01394-177">Authentifizierung mit einem OpenID Connect- und OAuth 2.0-Identitätsanbieter</span><span class="sxs-lookup"><span data-stu-id="01394-177">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="01394-178">Wenn Benutzerinformationen in Azure Active Directory oder einer anderen Identitätslösung gespeichert werden, die OpenID Connect oder OAuth 2.0 verwendet, können Sie das Paket **Microsoft.AspNetCore.Authentication.OpenIdConnect** für die Authentifizierung mithilfe des OpenID Connect-Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="01394-178">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="01394-179">Um sich z.B. beim Identity.Api-Microservice in eShopOnContainers zu authentifizieren, kann eine ASP.NET Core-Webanwendung, wie in folgendem vereinfachtem Beispiel in `Startup.cs` gezeigt, Middleware aus diesem Paket verwenden:</span><span class="sxs-lookup"><span data-stu-id="01394-179">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");
    var sessionCookieLifetime = Configuration.GetValue("SessionCookieLifetimeMinutes", 60);

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
    })
    .AddCookie(setup => setup.ExpireTimeSpan = TimeSpan.FromMinutes(sessionCookieLifetime))
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl.ToString();
        options.SignedOutRedirectUri = callBackUrl.ToString();
        options.ClientId = useLoadTest ? "mvctest" : "mvc";
        options.ClientSecret = "secret";
        options.ResponseType = useLoadTest ? "code id_token token" : "code id_token";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="01394-180">Beachten Sie, dass wenn Sie diesen Workflow verwenden, die ASP.NET Core Identity-Middleware nicht erforderlich ist, da der gesamte Speicher und die Authentifizierung der Benutzerinformationen vom Identitätsdienst behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="01394-180">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="01394-181">Ausstellen von Sicherheitstoken von einem ASP.NET Core-Dienst</span><span class="sxs-lookup"><span data-stu-id="01394-181">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="01394-182">Wenn Sie lieber Sicherheitstoken für lokale ASP.NET Core Identity-Benutzer ausstellen möchten, anstatt einen externen Identitätsanbieter zu verwenden, können Sie von einigen guten Bibliotheken von Drittanbietern profitieren.</span><span class="sxs-lookup"><span data-stu-id="01394-182">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="01394-183">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) und [OpenIddict](https://github.com/openiddict/openiddict-core) sind OpenID Connect-Anbieter, die sich einfach in ASP.NET Core Identity integrieren lassen, damit Sie Sicherheitstoken von einem ASP.NET Core-Dienst ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="01394-183">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="01394-184">Die [IdentityServer4-Dokumentation](https://identityserver4.readthedocs.io/en/latest/) bietet detaillierte Anweisungen zur Verwendung der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="01394-184">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="01394-185">Jedoch sind die grundlegenden Schritte zur Verwendung von IdentityServer4 zur Ausstellung von Token wie folgt.</span><span class="sxs-lookup"><span data-stu-id="01394-185">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="01394-186">Sie können UseIdentityServer in der Startup.Configure-Methode aufrufen, um IdentityServer4 der HTTP_Anforderungsverarbeitungspipeline hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="01394-186">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application's HTTP request processing pipeline.</span></span> <span data-ttu-id="01394-187">Dadurch kann die Bibliothek Anforderungen an OpenID Connect und OAuth2-Endpunkte wie „/connect/token“ verarbeiten</span><span class="sxs-lookup"><span data-stu-id="01394-187">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="01394-188">Sie konfigurieren IdentityServer4 in Startup.ConfigureServices, indem Sie services.AddIdentityServer aufrufen.</span><span class="sxs-lookup"><span data-stu-id="01394-188">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="01394-189">Sie konfigurieren Identitätsserver, indem Sie folgende Daten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="01394-189">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="01394-190">Die zu verwendenden [Anmeldeinformationen](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="01394-190">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="01394-191">Die [Identitäts- und API-Ressourcen](https://identityserver4.readthedocs.io/en/latest/topics/resources.html), auf die Benutzer möglicherweise Zugriff anfordern:</span><span class="sxs-lookup"><span data-stu-id="01394-191">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="01394-192">API-Ressourcen stellen geschützte Daten oder Funktionen dar, auf die ein Benutzer mit einem Zugriffstoken zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="01394-192">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="01394-193">Ein Beispiel einer API-Ressource wäre eine Web-API (oder ein Satz von APIs), für die die Autorisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="01394-193">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="01394-194">Identitätsressourcen stellen Informationen (Ansprüche) dar, die einem Client zur Identifizierung eines Benutzers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="01394-194">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="01394-195">Die Ansprüche können den Benutzernamen, die E-Mail-Adresse usw. beinhalten.</span><span class="sxs-lookup"><span data-stu-id="01394-195">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="01394-196">Die [Clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html), die eine Verbindung herstellen, um Token anzufordern.</span><span class="sxs-lookup"><span data-stu-id="01394-196">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="01394-197">Der Speichermechanismus für Benutzerinformationen, z.B. [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) oder eine Alternative.</span><span class="sxs-lookup"><span data-stu-id="01394-197">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="01394-198">Wenn Sie Clients und Ressourcen angeben, die IdentityServer4 verwenden sollen, können Sie eine <xref:System.Collections.Generic.IEnumerable%601>-Auflistung der geeigneten Typen an Methoden übergeben, die einen In-Memory-Client oder Ressourcenspeicher übernehmen.</span><span class="sxs-lookup"><span data-stu-id="01394-198">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="01394-199">Für komplexere Szenarios können Sie auch Client- oder Ressourcenanbietertypen über eine Abhängigkeitsinjektion nutzen.</span><span class="sxs-lookup"><span data-stu-id="01394-199">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="01394-200">Eine Beispielkonfiguration für IdentityServer4 zur Verwendung von In-Memory-Ressourcen und -Clients, die von einem benutzerdefinierten IClientStore-Typen bereitgestellt werden, könnten wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="01394-200">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //...
    services.AddSingleton<IClientStore, CustomClientStore>();
    services.AddIdentityServer()
        .AddSigningCredential("CN=sts")
        .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
        .AddAspNetIdentity<ApplicationUser>();
    //...
}
```

### <a name="consume-security-tokens"></a><span data-ttu-id="01394-201">Nutzen von Sicherheitstoken</span><span class="sxs-lookup"><span data-stu-id="01394-201">Consume security tokens</span></span>

<span data-ttu-id="01394-202">Die Authentifizierung bei einem OpenID Connect-Endpunkt oder die Ausstellung Ihrer eigenen Sicherheitstoken deckt einige Szenarios ab.</span><span class="sxs-lookup"><span data-stu-id="01394-202">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="01394-203">Was ist jedoch mit dem Dienst, der einfach nur den Zugriff für jene Benutzer einschränken muss, die über gültige Sicherheitstoken verfügen, die von einem anderen Dienst bereitgestellt wurden?</span><span class="sxs-lookup"><span data-stu-id="01394-203">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="01394-204">Für dieses Szenario ist die Middleware zur Authentifizierung, die JWT-Token behandelt, im **Microsoft.AspNetCore.Authentication.JwtBearer**-Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01394-204">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="01394-205">JWT steht für „[JSON Web Token](https://tools.ietf.org/html/rfc7519)“ und ist ein allgemeines Sicherheitstokenformat (definiert von RFC 7519) zum Kommunizieren von Sicherheitsansprüchen.</span><span class="sxs-lookup"><span data-stu-id="01394-205">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="01394-206">Vereinfacht sieht ein Beispiel zur Verwendung von Middleware zur Nutzung solcher Token etwa wie dieses Codefragment aus, das dem Ordering.Api-Microservice von eShopOnContainers entnommen ist.</span><span class="sxs-lookup"><span data-stu-id="01394-206">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="01394-207">Die Parameter hier sind:</span><span class="sxs-lookup"><span data-stu-id="01394-207">The parameters in this usage are:</span></span>

- <span data-ttu-id="01394-208">`Audience` stellt den Empfänger des eingehenden Tokens oder der Ressource dar, für die das Token den Zugriff erteilt.</span><span class="sxs-lookup"><span data-stu-id="01394-208">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="01394-209">Wenn der in diesem Wert angegebene Parameter nicht mit dem Parameter im Token übereinstimmt, wird das Token abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="01394-209">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="01394-210">`Authority` ist die Adresse des Authentifizierungsservers, der Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="01394-210">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="01394-211">Die Middleware zur JWT-Bearerauthentifizierung verwendet diesen URI, um den öffentlichen Schlüssel abzurufen, der zur Überprüfung der Tokensignatur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="01394-211">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="01394-212">Die Middleware bestätigt auch, dass der `iss`-Parameter im Token mit diesem URI übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="01394-212">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="01394-213">Ein weiterer Parameter, `RequireHttpsMetadata`, ist für Testzwecke nützlich: Sie legen diesen Parameter auf FALSE fest, damit Sie Tests in Umgebungen durchführen können, in denen Sie keine Zertifikate besitzen.</span><span class="sxs-lookup"><span data-stu-id="01394-213">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="01394-214">In realen Bereitstellungen dürfen JWT-Bearertoken immer nur über HTTPS übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="01394-214">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="01394-215">Wenn diese Middleware vorhanden ist, werden JWT-Token automatisch aus Autorisierungsheadern extrahiert.</span><span class="sxs-lookup"><span data-stu-id="01394-215">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="01394-216">Sie werden anschließend deserialisiert, überprüft (mithilfe der Werte in den Parametern `Audience` und `Authority`) und als Benutzerinformation gespeichert, auf die später durch MVC-Aktionen oder Autorisierungsfilter verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="01394-216">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="01394-217">Die Middleware für die JWT-Bearerauthentifizierung kann auch erweiterte Szenarios unterstützen, beispielsweise die Verwendung eines lokalen Zertifikats zur Überprüfung eines Tokens, wenn die Registrierungsstelle nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="01394-217">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="01394-218">Für dieses Szenario können Sie ein `TokenValidationParameters`-Objekt im `JwtBearerOptions`-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="01394-218">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01394-219">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="01394-219">Additional resources</span></span>

- <span data-ttu-id="01394-220">**Gemeinsames Verwenden von Cookies in mehreren Anwendungen** </span><span class="sxs-lookup"><span data-stu-id="01394-220">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="01394-221">**Einführung in Identität** </span><span class="sxs-lookup"><span data-stu-id="01394-221">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="01394-222">**Rick Anderson. Zweistufige Authentifizierung mit SMS** </span><span class="sxs-lookup"><span data-stu-id="01394-222">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="01394-223">**Enabling authentication using Facebook, Google and other external providers (Ermöglichen der Authentifizierung mit Facebook, Google und anderen externen Anbietern)**  </span><span class="sxs-lookup"><span data-stu-id="01394-223">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="01394-224">**Michell Anicas. An Introduction to OAuth 2 (Einführung in OAuth 2)**  </span><span class="sxs-lookup"><span data-stu-id="01394-224">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="01394-225">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span><span class="sxs-lookup"><span data-stu-id="01394-225">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="01394-226">**IdentityServer4. Offizielle Dokumentation** </span><span class="sxs-lookup"><span data-stu-id="01394-226">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="01394-227">[Zurück](../implement-resilient-applications/monitor-app-health.md)
>[Weiter](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="01394-227">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
