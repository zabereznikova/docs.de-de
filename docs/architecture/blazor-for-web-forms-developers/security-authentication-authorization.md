---
title: 'Sicherheit: Authentifizierung und Autorisierung in ASP.net Web Forms und Blazor'
description: Erfahren Sie, wie Sie die Authentifizierung und Autorisierung in ASP.net Web Forms und behandeln Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 690e559617e4961c3cf3262a6d2d48a6bfac67cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161294"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a><span data-ttu-id="5545e-103">Sicherheit: Authentifizierung und Autorisierung in ASP.NET Web Forms und Blazor </span><span class="sxs-lookup"><span data-stu-id="5545e-103">Security: Authentication and Authorization in ASP.NET Web Forms and Blazor</span></span>

<span data-ttu-id="5545e-104">Das Migrieren von einer ASP.net-Web Forms Anwendung zu Blazor erfordert fast sicherlich die Aktualisierung der Authentifizierung und Autorisierung, vorausgesetzt, die Anwendung hätte die Authentifizierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5545e-104">Migrating from an ASP.NET Web Forms application to Blazor will almost certainly require updating how authentication and authorization is performed, assuming the application had authentication configured.</span></span> <span data-ttu-id="5545e-105">In diesem Kapitel wird erläutert, wie Sie aus dem ASP.net Web Forms Universal Provider-Modell (für Mitgliedschaften, Rollen und Benutzerprofile) migrieren und wie Sie mit ASP.net Core Identität von Blazor apps arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5545e-105">This chapter will cover how to migrate from the ASP.NET Web Forms universal provider model (for membership, roles, and user profiles) and how to work with ASP.NET Core Identity from Blazor apps.</span></span> <span data-ttu-id="5545e-106">In diesem Kapitel werden allgemeine Schritte und Überlegungen behandelt, die ausführlichen Schritte und Skripts finden Sie in der Dokumentation, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5545e-106">While this chapter will cover the high level steps and considerations, the detailed steps and scripts may be found in the referenced documentation.</span></span>

## <a name="aspnet-universal-providers"></a><span data-ttu-id="5545e-107">ASP.net universelle Anbieter</span><span class="sxs-lookup"><span data-stu-id="5545e-107">ASP.NET universal providers</span></span>

<span data-ttu-id="5545e-108">Seit ASP.NET 2,0 hat die ASP.net-Web Forms Plattform ein Anbieter Modell für eine Vielzahl von Features unterstützt, einschließlich der Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="5545e-108">Since ASP.NET 2.0, the ASP.NET Web Forms platform has supported a provider model for a variety of features, including membership.</span></span> <span data-ttu-id="5545e-109">Der universelle Mitgliedschafts Anbieter wird zusammen mit dem optionalen Rollen Anbieter häufig mit ASP.net-Web Forms Anwendungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5545e-109">The universal membership provider, along with the optional role provider, is very commonly deployed with ASP.NET Web Forms applications.</span></span> <span data-ttu-id="5545e-110">Er bietet eine robuste und sichere Möglichkeit zum Verwalten der Authentifizierung und Autorisierung, die noch heute gut funktionieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-110">It offers a robust and secure way to manage authentication and authorization that continues to work well today.</span></span> <span data-ttu-id="5545e-111">Das aktuelle Angebot dieser universellen Anbieter steht als nuget-Paket [Microsoft. Aspnet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5545e-111">The most recent offering of these universal providers is available as a NuGet package, [Microsoft.AspNet.Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span></span>

<span data-ttu-id="5545e-112">Die universelle Anbieter arbeiten mit einem SQL-Datenbankschema, das Tabellen wie `aspnet_Applications` ,, `aspnet_Membership` und enthält `aspnet_Roles` `aspnet_Users` .</span><span class="sxs-lookup"><span data-stu-id="5545e-112">The Universal Providers work with a SQL database schema that includes tables like `aspnet_Applications`, `aspnet_Membership`, `aspnet_Roles`, and `aspnet_Users`.</span></span> <span data-ttu-id="5545e-113">Bei der Konfiguration durch Ausführen des [aspnet_regsql.exe Befehls](/previous-versions/ms229862(v=vs.140))installieren die Anbieter Tabellen und gespeicherte Prozeduren, die alle erforderlichen Abfragen und Befehle bereitstellen, die für die Arbeit mit den zugrunde liegenden Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5545e-113">When configured by running the [aspnet_regsql.exe command](/previous-versions/ms229862(v=vs.140)), the providers install tables and stored procedures that provide all of the necessary queries and commands necessary to work with the underlying data.</span></span> <span data-ttu-id="5545e-114">Das Datenbankschema und diese gespeicherten Prozeduren sind nicht mit neueren ASP.net Identity und ASP.net Core Identitäts Systemen kompatibel, sodass vorhandene Daten in das neue System migriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5545e-114">The database schema and these stored procedures are not compatible with newer ASP.NET Identity and ASP.NET Core Identity systems, so existing data must be migrated into the new system.</span></span> <span data-ttu-id="5545e-115">Abbildung 1 zeigt ein Beispiel für ein Tabellen Schema, das für universelle Anbieter konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="5545e-115">Figure 1 shows an example table schema configured for universal providers.</span></span>

![Schema für universelle Anbieter](./media/security/membership-tables.png)

<span data-ttu-id="5545e-117">Der universelle Anbieter übernimmt Benutzer, Mitgliedschaft, Rollen und Profile.</span><span class="sxs-lookup"><span data-stu-id="5545e-117">The universal provider handles users, membership, roles, and profiles.</span></span> <span data-ttu-id="5545e-118">Benutzern werden global eindeutige Bezeichner zugewiesen, und grundlegende Informationen (UserID, username) werden in der `aspnet_Users` Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5545e-118">Users are assigned globally unique identifiers and very basic information (userId, userName) is stored in the `aspnet_Users` table.</span></span> <span data-ttu-id="5545e-119">Authentifizierungsinformationen, wie z. b. das Kennwort, das Kenn Wort Format, das Kennwort Salt, Sperr Indikatoren und Details usw. werden in der `aspnet_Membership` Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5545e-119">Authentication information, such as password, password format, password salt, lockout counters and details, etc. are stored in the `aspnet_Membership` table.</span></span> <span data-ttu-id="5545e-120">Rollen bestehen einfach aus Namen und eindeutigen bezeichnerids, die Benutzern über die Zuordnungs Tabelle zugewiesen werden und `aspnet_UsersInRoles` eine m:n-Beziehung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5545e-120">Roles consist simply of names and unique identifiers, which are assigned to users via the `aspnet_UsersInRoles` association table, providing a many-to-many relationship.</span></span>

<span data-ttu-id="5545e-121">Wenn Ihr vorhandenes System zusätzlich zur Mitgliedschaft Rollen verwendet, müssen Sie die Benutzerkonten, die zugehörigen Kenn Wörter, die Rollen und die Rollen Mitgliedschaft in ASP.net Core Identität migrieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-121">If your existing system is using roles in addition to membership, you will need to migrate the user accounts, the associated passwords, the roles, and the role membership into ASP.NET Core Identity.</span></span> <span data-ttu-id="5545e-122">Sie müssen wahrscheinlich auch Ihren Code aktualisieren, bei dem Sie zurzeit Rollen Überprüfungen durchführen, indem Sie if-Anweisungen verwenden, um stattdessen deklarative Filter, Attribute und/oder taghilfsprogramme zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="5545e-122">You will also most likely need to update your code where you're currently performing role checks using if statements to instead leverage declarative filters, attributes, and/or tag helpers.</span></span> <span data-ttu-id="5545e-123">Am Ende dieses Kapitels werden die Migrations Überlegungen ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="5545e-123">We will review migration considerations in greater detail at the end of this chapter.</span></span>

### <a name="authorization-configuration-in-web-forms"></a><span data-ttu-id="5545e-124">Autorisierungs Konfiguration in Web Forms</span><span class="sxs-lookup"><span data-stu-id="5545e-124">Authorization configuration in Web Forms</span></span>

<span data-ttu-id="5545e-125">Um den autorisierten Zugriff auf bestimmte Seiten in einer ASP.net-Web Forms Anwendung zu konfigurieren, geben Sie in der Regel an, dass anonyme Benutzer auf bestimmte Seiten oder Ordner nicht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5545e-125">To configure authorized access to certain pages in an ASP.NET Web Forms application, typically you specify that certain pages or folders are inaccessible to anonymous users.</span></span> <span data-ttu-id="5545e-126">Dies erfolgt in der web.config-Datei:</span><span class="sxs-lookup"><span data-stu-id="5545e-126">This is done in the web.config file:</span></span>

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

<span data-ttu-id="5545e-127">Der `authentication` Konfigurations Abschnitt richtet die Formular Authentifizierung für die Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="5545e-127">The `authentication` configuration section sets up forms authentication for the application.</span></span> <span data-ttu-id="5545e-128">Der `authorization` Abschnitt wird verwendet, um anonyme Benutzer nicht für die gesamte Anwendung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="5545e-128">The `authorization` section is used to disallow anonymous users for the entire application.</span></span> <span data-ttu-id="5545e-129">Sie können jedoch präzisetere Autorisierungs Regeln pro Standort bereitstellen und rollenbasierte Autorisierungs Überprüfungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="5545e-129">However, you can provide more granular authorization rules on a per-location basis as well as apply role based authorization checks.</span></span>

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="5545e-130">Wenn die obige Konfiguration mit der ersten Konfiguration kombiniert wird, können anonyme Benutzer auf die Anmeldeseite zugreifen und die Website weite Einschränkung für nicht authentifizierte Benutzer überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5545e-130">The above configuration, when combined with the first one, would allow anonymous users to access the login page, overriding the site-wide restriction on non-authenticated users.</span></span>

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

<span data-ttu-id="5545e-131">Die obige Konfiguration, in Kombination mit den anderen, schränkt den Zugriff auf den `/admin` Ordner und alle darin enthaltenen Ressourcen auf Mitglieder der Rolle "Administratoren" ein.</span><span class="sxs-lookup"><span data-stu-id="5545e-131">The above configuration, when combined with the others, restricts access to the `/admin` folder and all resources within it to members of the "Administrators" role.</span></span> <span data-ttu-id="5545e-132">Dies kann auch durch das Platzieren einer separaten `web.config` Datei innerhalb des Ordner Stamms angewendet werden `/admin` .</span><span class="sxs-lookup"><span data-stu-id="5545e-132">This could also be applied by placing a separate `web.config` file within the `/admin` folder root.</span></span>

### <a name="authorization-code-in-web-forms"></a><span data-ttu-id="5545e-133">Autorisierungs Code in Web Forms</span><span class="sxs-lookup"><span data-stu-id="5545e-133">Authorization code in Web Forms</span></span>

<span data-ttu-id="5545e-134">Zusätzlich zum Konfigurieren des Zugriffs mithilfe von `web.config` können Sie den Zugriff und das Verhalten in Ihrer Web Forms Anwendung auch Programm gesteuert konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-134">In addition to configuring access using `web.config`, you can also programmatically configure access and behavior in your Web Forms application.</span></span> <span data-ttu-id="5545e-135">Beispielsweise können Sie die Fähigkeit einschränken, bestimmte Vorgänge auszuführen oder bestimmte Daten basierend auf der Rolle des Benutzers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5545e-135">For instance, you can restrict the ability to perform certain operations or view certain data based on the user's role.</span></span>

<span data-ttu-id="5545e-136">Dieser Code kann sowohl in der Code Behind-Logik als auch auf der Seite selbst verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5545e-136">This code can be used both in codebehind logic as well as in the page itself:</span></span>

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

<span data-ttu-id="5545e-137">Zusätzlich zum Überprüfen der Mitgliedschaft in Benutzer Rollen können Sie auch feststellen, ob Sie authentifiziert sind (Dies ist jedoch oft besser durch die oben beschriebene standortbasierte Konfiguration möglich).</span><span class="sxs-lookup"><span data-stu-id="5545e-137">In addition to checking user role membership, you can also determine if they are authenticated (though often this is better done using the location-based configuration covered above).</span></span> <span data-ttu-id="5545e-138">Im folgenden finden Sie ein Beispiel für diesen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="5545e-138">Below is an example of this approach.</span></span>

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

<span data-ttu-id="5545e-139">Im obigen Code wird die rollenbasierte Zugriffs Steuerung (Role-Based Access Control, RBAC) verwendet, um zu bestimmen, ob bestimmte Elemente der Seite, z. b. `SecretPanel` , basierend auf der Rolle des aktuellen Benutzers sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="5545e-139">In the code above, role-based access control (RBAC) is used to determine whether certain elements of the page, such as a `SecretPanel`, are visible based on the current user's role.</span></span>

<span data-ttu-id="5545e-140">In der Regel konfigurieren ASP.net Web Forms Anwendungen die Sicherheit innerhalb der `web.config` Datei und fügen dann bei Bedarf zusätzliche Überprüfungen für `.aspx` Seiten und zugehörige `.aspx.cs` Code Behind-Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="5545e-140">Typically, ASP.NET Web Forms applications configure security within the `web.config` file and then add additional checks where needed in `.aspx` pages and their related `.aspx.cs` codebehind files.</span></span> <span data-ttu-id="5545e-141">Die meisten Anwendungen nutzen den universellen Mitgliedschafts Anbieter, häufig mit dem zusätzlichen Rollen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="5545e-141">Most applications leverage the universal membership provider, frequently with the additional role provider.</span></span>

## <a name="aspnet-core-identity"></a><span data-ttu-id="5545e-142">ASP.NET Core-Identität</span><span class="sxs-lookup"><span data-stu-id="5545e-142">ASP.NET Core Identity</span></span>

<span data-ttu-id="5545e-143">Obwohl die Authentifizierung und Autorisierung weiterhin verwendet wird, verwendet ASP.net Core Identität im Vergleich zu den universellen Anbietern einen anderen Satz Abstraktionen und Annahmen.</span><span class="sxs-lookup"><span data-stu-id="5545e-143">Although still tasked with authentication and authorization, ASP.NET Core Identity uses a different set of abstractions and assumptions when compared to the universal providers.</span></span> <span data-ttu-id="5545e-144">Beispielsweise unterstützt das neue Identitäts Modell die Authentifizierung von Drittanbietern, sodass sich Benutzer mit einem Social Media-Konto oder einem anderen vertrauenswürdigen Authentifizierungs Anbieter authentifizieren können.</span><span class="sxs-lookup"><span data-stu-id="5545e-144">For example, the new Identity model supports third party authentication, allowing users to authenticate using a social media account or other trusted authentication provider.</span></span> <span data-ttu-id="5545e-145">ASP.net Core Identity unterstützt die Benutzeroberfläche für häufig benötigte Seiten wie Login, Logout und Register.</span><span class="sxs-lookup"><span data-stu-id="5545e-145">ASP.NET Core Identity supports UI for commonly needed pages like login, logout, and register.</span></span> <span data-ttu-id="5545e-146">Er nutzt EF Core für den Datenzugriff und verwendet EF Core Migrationen, um das erforderliche Schema zu generieren, das für die Unterstützung des Datenmodells erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5545e-146">It leverages EF Core for its data access, and uses EF Core migrations to generate the necessary schema required to supports its data model.</span></span> <span data-ttu-id="5545e-147">Diese [Einführung in die Identität auf ASP.net Core](/aspnet/core/security/authentication/identity) bietet einen guten Überblick darüber, was in ASP.net Core Identity enthalten ist und wie Sie mit der Arbeit beginnen können.</span><span class="sxs-lookup"><span data-stu-id="5545e-147">This [introduction to Identity on ASP.NET Core](/aspnet/core/security/authentication/identity) provides a good overview of what is included with ASP.NET Core Identity and how to get started working with it.</span></span> <span data-ttu-id="5545e-148">Wenn Sie nicht bereits ASP.net Core Identität in Ihrer Anwendung und der zugehörigen Datenbank eingerichtet haben, wird Ihnen der Einstieg erleichtern.</span><span class="sxs-lookup"><span data-stu-id="5545e-148">If you haven't already set up ASP.NET Core Identity in your application and its database, it will help you get started.</span></span>

### <a name="roles-claims-and-policies"></a><span data-ttu-id="5545e-149">Rollen, Ansprüche und Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5545e-149">Roles, claims, and policies</span></span>

<span data-ttu-id="5545e-150">Sowohl universelle Anbieter als auch ASP.net Core Identität unterstützen das Konzept der Rollen.</span><span class="sxs-lookup"><span data-stu-id="5545e-150">Both the universal providers and ASP.NET Core Identity support the concept of roles.</span></span> <span data-ttu-id="5545e-151">Sie können Rollen für Benutzer erstellen und Rollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5545e-151">You can create roles for users and assign users to roles.</span></span> <span data-ttu-id="5545e-152">Benutzer können zu einer beliebigen Anzahl von Rollen gehören, und Sie können die Rollen Mitgliedschaft im Rahmen der Autorisierungs Implementierung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5545e-152">Users can belong to any number of roles, and you can verify role membership as part of your authorization implementation.</span></span>

<span data-ttu-id="5545e-153">Zusätzlich zu den Rollen unterstützt ASP.net Core Identity die Konzepte von Ansprüchen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="5545e-153">In addition to roles, ASP.NET Core identity supports the concepts of claims and policies.</span></span> <span data-ttu-id="5545e-154">Obwohl eine Rolle speziell einem Satz von Ressourcen entsprechen sollte, auf die ein Benutzer in dieser Rolle zugreifen kann, ist ein Anspruch einfach Teil der Identität eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5545e-154">While a role should specifically correspond to a set of resources a user in that role should be able to access, a claim is simply part of a user's identity.</span></span> <span data-ttu-id="5545e-155">Ein Anspruch ist ein Name-Wert-Paar, das den Betreff darstellt, nicht das, was der Betreff tun kann.</span><span class="sxs-lookup"><span data-stu-id="5545e-155">A claim is a name value pair that represents what the subject is, not what the subject can do.</span></span>

<span data-ttu-id="5545e-156">Es ist möglich, die Ansprüche eines Benutzers direkt zu überprüfen und anhand dieser festzustellen, ob einem Benutzer Zugriff auf eine Ressource gewährt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5545e-156">It is possible to directly inspect a user's claims and determine based on these whether a user should be given access to a resource.</span></span> <span data-ttu-id="5545e-157">Diese Überprüfungen werden jedoch häufig wiederholt und im gesamten System verstreut.</span><span class="sxs-lookup"><span data-stu-id="5545e-157">However, such checks are often repetitive and scattered throughout the system.</span></span> <span data-ttu-id="5545e-158">Ein besserer Ansatz besteht darin, eine *Richtlinie*zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-158">A better approach is to define a *policy*.</span></span>

<span data-ttu-id="5545e-159">Eine Autorisierungs Richtlinie besteht aus einer oder mehreren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="5545e-159">An authorization policy consists of one or more requirements.</span></span> <span data-ttu-id="5545e-160">Richtlinien werden als Teil der Autorisierungs Dienst Konfiguration in der- `ConfigureServices` Methode von registriert `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="5545e-160">Policies are registered as part of the authorization service configuration in the `ConfigureServices` method of `Startup.cs`.</span></span> <span data-ttu-id="5545e-161">Der folgende Code Ausschnitt konfiguriert z. b. eine Richtlinie mit dem Namen "canadiansonly", die die Anforderung hat, dass der Benutzer über den Anspruch "Country" mit dem Wert "Canada" verfügt.</span><span class="sxs-lookup"><span data-stu-id="5545e-161">For example, the following code snippet configures a policy called "CanadiansOnly" which has the requirement that the user have the Country claim with the value of "Canada".</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

<span data-ttu-id="5545e-162">[Weitere Informationen zum Erstellen von benutzerdefinierten Richtlinien finden Sie in der-Dokumentation](/aspnet/core/security/authorization/policies).</span><span class="sxs-lookup"><span data-stu-id="5545e-162">You can [learn more about how to create custom policies in the documentation](/aspnet/core/security/authorization/policies).</span></span>

<span data-ttu-id="5545e-163">Unabhängig davon, ob Sie Richtlinien oder Rollen verwenden, können Sie angeben, dass eine bestimmte Seite in Blazor der Anwendung eine Rolle oder Richtlinie mit dem- `[Authorize]` Attribut erfordert, das mit der- `@attribute` Direktive angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5545e-163">Whether you're using policies or roles, you can specify that a particular page in your Blazor application require that role or policy with the `[Authorize]` attribute, applied with the `@attribute` directive.</span></span>

<span data-ttu-id="5545e-164">Erfordert eine Rolle:</span><span class="sxs-lookup"><span data-stu-id="5545e-164">Requiring a role:</span></span>

```csharp
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="5545e-165">Das Verlangen einer Richtlinie muss erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="5545e-165">Requiring a policy be satisfied:</span></span>

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

<span data-ttu-id="5545e-166">Wenn Sie Zugriff auf den Authentifizierungs Zustand, die Rollen oder Ansprüche eines Benutzers in Ihrem Code benötigen, gibt es zwei Möglichkeiten, dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5545e-166">If you need access to a user's authentication state, roles, or claims in your code, there are two primary ways to achieve this.</span></span> <span data-ttu-id="5545e-167">Der erste besteht darin, den Authentifizierungs Status als kaskadierenden Parameter zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="5545e-167">The first is to receive the authentication state as a cascading parameter.</span></span> <span data-ttu-id="5545e-168">Die zweite besteht darin, mithilfe eines eingefügten auf den Zustand zuzugreifen `AuthenticationStateProvider` .</span><span class="sxs-lookup"><span data-stu-id="5545e-168">The second is to access the state using an injected `AuthenticationStateProvider`.</span></span> <span data-ttu-id="5545e-169">Die Details zu den einzelnen Ansätzen werden in der Dokumentation zur [ Blazor Sicherheit](/aspnet/core/blazor/security/)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5545e-169">The details of each of these approaches are described in the [Blazor Security documentation](/aspnet/core/blazor/security/).</span></span>

<span data-ttu-id="5545e-170">Der folgende Code zeigt, wie der `AuthenticationState` als kaskadierenden Parameter empfangen wird:</span><span class="sxs-lookup"><span data-stu-id="5545e-170">The following code shows how to receive the `AuthenticationState` as a cascading parameter:</span></span>

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

<span data-ttu-id="5545e-171">Mit diesem Parameter können Sie den Benutzer mit dem folgenden Code aufrufen:</span><span class="sxs-lookup"><span data-stu-id="5545e-171">With this parameter in place, you can get the user using this code:</span></span>

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

<span data-ttu-id="5545e-172">Der folgende Code zeigt, wie Sie einfügen `AuthenticationStateProvider` :</span><span class="sxs-lookup"><span data-stu-id="5545e-172">The following code shows how to inject the `AuthenticationStateProvider`:</span></span>

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

<span data-ttu-id="5545e-173">Wenn der Anbieter vorhanden ist, können Sie mit folgendem Code auf den Benutzer zugreifen:</span><span class="sxs-lookup"><span data-stu-id="5545e-173">With the provider in place, you can gain access to the user with the following code:</span></span>

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

<span data-ttu-id="5545e-174">**Hinweis:** Die `AuthorizeView` weiter unten in diesem Kapitel behandelte Komponente bietet eine deklarative Möglichkeit, um zu steuern, was ein Benutzer auf einer Seite oder Komponente sieht.</span><span class="sxs-lookup"><span data-stu-id="5545e-174">**Note:** The `AuthorizeView` component, covered later in this chapter, provides a declarative way to control what a user sees on a page or component.</span></span>

<span data-ttu-id="5545e-175">Zum Arbeiten mit Benutzern und Ansprüchen (in Blazor Server Anwendungen) müssen Sie möglicherweise auch eine `UserManager<T>` ( `IdentityUser` standardmäßig verwenden) einfügen, die Sie zum Auflisten und Ändern von Ansprüchen für einen Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5545e-175">To work with users and claims (in Blazor Server applications) you may also need to inject a `UserManager<T>` (use `IdentityUser` for default) which you can use to enumerate and modify claims for a user.</span></span> <span data-ttu-id="5545e-176">Fügen Sie zuerst den-Typ ein, und weisen Sie ihn einer Eigenschaft zu:</span><span class="sxs-lookup"><span data-stu-id="5545e-176">First inject the type and assign it to a property:</span></span>

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

<span data-ttu-id="5545e-177">Verwenden Sie diese dann, um mit den Ansprüchen des Benutzers zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5545e-177">Then use it to work with the user's claims.</span></span> <span data-ttu-id="5545e-178">Im folgenden Beispiel wird gezeigt, wie ein Anspruch hinzugefügt und für einen Benutzer persistent gespeichert wird:</span><span class="sxs-lookup"><span data-stu-id="5545e-178">The following sample shows how to add and persist a claim on a user:</span></span>

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

<span data-ttu-id="5545e-179">Wenn Sie mit Rollen arbeiten müssen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="5545e-179">If you need to work with roles, follow the same approach.</span></span> <span data-ttu-id="5545e-180">Möglicherweise müssen Sie eine `RoleManager<T>` ( `IdentityRole` für den Standardtyp verwenden) einfügen, um die Rollen selbst aufzulisten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5545e-180">You may need to inject a `RoleManager<T>` (use `IdentityRole` for default type) to list and manage the roles themselves.</span></span>

<span data-ttu-id="5545e-181">**Hinweis:** In Blazor Webassembly-Projekten müssen Sie Server-APIs bereitstellen, um diese Vorgänge auszuführen (anstatt `UserManager<T>` oder direkt zu verwenden `RoleManager<T>` ).</span><span class="sxs-lookup"><span data-stu-id="5545e-181">**Note:** In Blazor WebAssembly projects, you will need to provide server APIs to perform these operations (instead of using `UserManager<T>` or `RoleManager<T>` directly).</span></span> <span data-ttu-id="5545e-182">Eine Blazor webassemblyclientanwendung verwaltet Ansprüche und/oder Rollen durch sicheres Aufrufen von API-Endpunkten, die für diesen Zweck verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5545e-182">A Blazor WebAssembly client application would manage claims and/or roles by securely calling API endpoints exposed for this purpose.</span></span>

### <a name="migration-guide"></a><span data-ttu-id="5545e-183">Migrationshandbuch</span><span class="sxs-lookup"><span data-stu-id="5545e-183">Migration guide</span></span>

<span data-ttu-id="5545e-184">Die Migration von ASP.net Web Forms und universellen Anbietern zu ASP.net Core Identity erfordert mehrere Schritte:</span><span class="sxs-lookup"><span data-stu-id="5545e-184">Migrating from ASP.NET Web Forms and universal providers to ASP.NET Core Identity requires several steps:</span></span>

1. <span data-ttu-id="5545e-185">Erstellen ASP.net Core Identitätsdaten Bank Schemas in der Zieldatenbank</span><span class="sxs-lookup"><span data-stu-id="5545e-185">Create ASP.NET Core Identity database schema in destination database</span></span>
2. <span data-ttu-id="5545e-186">Migrieren von Daten aus einem universellen Anbieter Schema in ASP.net Core Identitäts Schema</span><span class="sxs-lookup"><span data-stu-id="5545e-186">Migrate data from universal provider schema to ASP.NET Core Identity schema</span></span>
3. <span data-ttu-id="5545e-187">Migrieren der Konfiguration von web.config zu Middleware und Diensten, normalerweise in `Startup.cs`</span><span class="sxs-lookup"><span data-stu-id="5545e-187">Migrate configuration from web.config to middleware and services, typically in `Startup.cs`</span></span>
4. <span data-ttu-id="5545e-188">Aktualisieren einzelner Seiten mithilfe von Steuerelementen und Bedingungen zur Verwendung von taghilfsprogrammen und neuen Identitäts-APIs.</span><span class="sxs-lookup"><span data-stu-id="5545e-188">Update individual pages using controls and conditionals to use tag helpers and new identity APIs.</span></span>

<span data-ttu-id="5545e-189">Jeder dieser Schritte wird in den folgenden Abschnitten ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="5545e-189">Each of these steps is described in detail in the following sections.</span></span>

### <a name="creating-the-aspnet-core-identity-schema"></a><span data-ttu-id="5545e-190">Erstellen des ASP.net Core-Identitäts Schemas</span><span class="sxs-lookup"><span data-stu-id="5545e-190">Creating the ASP.NET Core Identity schema</span></span>

<span data-ttu-id="5545e-191">Es gibt mehrere Möglichkeiten, die erforderliche Tabellenstruktur zu erstellen, die für die ASP.net Core Identität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5545e-191">There are several ways to create the necessary table structure used for ASP.NET Core Identity.</span></span> <span data-ttu-id="5545e-192">Die einfachste Möglichkeit besteht darin, eine neue ASP.net Core-Webanwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5545e-192">The simplest is to create a new ASP.NET Core Web application.</span></span> <span data-ttu-id="5545e-193">Wählen Sie Webanwendung aus, und ändern Sie dann die Authentifizierung, sodass einzelne Benutzerkonten verwendet</span><span class="sxs-lookup"><span data-stu-id="5545e-193">Choose Web Application and then change Authentication to use Individual User Accounts.</span></span>

![Neues Projekt mit einzelnen Benutzerkonten](./media/security/individual-user-accounts.png)

<span data-ttu-id="5545e-195">In der Befehlszeile können Sie das gleiche tun, indem Sie Ausführen `dotnet new webapp -au Individual` .</span><span class="sxs-lookup"><span data-stu-id="5545e-195">From the command line, you can do the same thing by running `dotnet new webapp -au Individual`.</span></span> <span data-ttu-id="5545e-196">Nachdem die App erstellt wurde, führen Sie Sie aus, und registrieren Sie sich auf der Website.</span><span class="sxs-lookup"><span data-stu-id="5545e-196">Once the app has been created, run it and register on the site.</span></span> <span data-ttu-id="5545e-197">Sie sollten eine Seite wie die folgende ausführen:</span><span class="sxs-lookup"><span data-stu-id="5545e-197">You should trigger a page like the one shown below:</span></span>

![Migrations Seite anwenden](./media/security/apply-migrations-page.png)

<span data-ttu-id="5545e-199">Klicken Sie auf die Schaltfläche Migrations anwenden, und die erforderlichen Datenbanktabellen sollten für Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5545e-199">Click on the "Apply Migrations" button and the necessary database tables should be created for you.</span></span> <span data-ttu-id="5545e-200">Außerdem sollten die Migrations Dateien wie im folgenden dargestellt in Ihrem Projekt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="5545e-200">In addition, the migration files should appear in your project, as shown:</span></span>

![Migrations Dateien](./media/security/migration-files.png)

<span data-ttu-id="5545e-202">Mithilfe dieses Befehlszeilen Tools können Sie die Migration selbst ausführen, ohne die Webanwendung auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5545e-202">You can run the migration yourself, without running the web application, using this command line tool:</span></span>

```powershell
dotnet ef database update
```

<span data-ttu-id="5545e-203">Wenn Sie ein Skript zum Anwenden des neuen Schemas auf eine vorhandene Datenbank ausführen möchten, können Sie ein Skript für diese Migrationen von der Befehlszeile aus erstellen.</span><span class="sxs-lookup"><span data-stu-id="5545e-203">If you would rather run a script to apply the new schema to an existing database, you can script these migrations from the command line.</span></span> <span data-ttu-id="5545e-204">Führen Sie diesen Befehl aus, um das Skript zu generieren:</span><span class="sxs-lookup"><span data-stu-id="5545e-204">Run this command to generate the script:</span></span>

```powershell
dotnet ef migrations script -o auth.sql
```

<span data-ttu-id="5545e-205">Dadurch wird ein SQL-Skript in der Ausgabedatei erstellt `auth.sql` , das dann für die gewünschte Datenbank ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5545e-205">This will produce a SQL script in the output file `auth.sql` which can then be run against whatever database you like.</span></span> <span data-ttu-id="5545e-206">Wenn Sie Probleme beim Ausführen von `dotnet ef` Befehlen haben, [Stellen Sie sicher, dass Sie die EF Core Tools auf Ihrem System installiert haben](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="5545e-206">If you have any trouble running `dotnet ef` commands, [make sure you have the EF Core tools installed on your system](/ef/core/miscellaneous/cli/dotnet).</span></span>

<span data-ttu-id="5545e-207">Wenn Sie über zusätzliche Spalten in ihren Quell Tabellen verfügen, müssen Sie den besten Speicherort für diese Spalten im neuen Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="5545e-207">In the event you have additional columns on your source tables, you will need to identify the best location for these columns in the new schema.</span></span> <span data-ttu-id="5545e-208">Im Allgemeinen sollten in der Tabelle gefundene Spalten `aspnet_Membership` der Tabelle zugeordnet werden `AspNetUsers` .</span><span class="sxs-lookup"><span data-stu-id="5545e-208">Generally, columns found on the `aspnet_Membership` table should be mapped to the `AspNetUsers` table.</span></span> <span data-ttu-id="5545e-209">Spalten in `aspnet_Roles` sollten zugeordnet werden `AspNetRoles` .</span><span class="sxs-lookup"><span data-stu-id="5545e-209">Columns on `aspnet_Roles` should be mapped to `AspNetRoles`.</span></span> <span data-ttu-id="5545e-210">Alle weiteren Spalten in der `aspnet_UsersInRoles` Tabelle werden der Tabelle hinzugefügt `AspNetUserRoles` .</span><span class="sxs-lookup"><span data-stu-id="5545e-210">Any additional columns on the `aspnet_UsersInRoles` table would be added to the `AspNetUserRoles` table.</span></span>

<span data-ttu-id="5545e-211">Außerdem sollten Sie erwägen, zusätzliche Spalten in separaten Tabellen zu platzieren, damit zukünftige Migrationen keine solchen Anpassungen des Standard Identitäts Schemas berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="5545e-211">It's also worth considering putting any additional columns on separate tables, so that future migrations won't need to take into account such customizations of the default identity schema.</span></span>

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a><span data-ttu-id="5545e-212">Migrieren von Daten von universellen Anbietern in ASP.net Core Identität</span><span class="sxs-lookup"><span data-stu-id="5545e-212">Migrating data from universal providers to ASP.NET Core Identity</span></span>

<span data-ttu-id="5545e-213">Wenn das Ziel Tabellen Schema vorhanden ist, besteht der nächste Schritt darin, die Benutzer-und Rollen Einträge zum neuen Schema zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-213">Once you have the destination table schema in place, the next step is to migrate your user and role records to the new schema.</span></span> <span data-ttu-id="5545e-214">Eine komplette Liste der Schema Unterschiede, einschließlich der Spalten, denen neue Spalten zugeordnet werden, finden Sie [hier](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span><span class="sxs-lookup"><span data-stu-id="5545e-214">A complete list of the schema differences, including which columns map to which new columns, can be found [here](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span>

<span data-ttu-id="5545e-215">Wenn Sie Ihre Benutzer von der Mitgliedschaft zu den neuen Identitäts Tabellen migrieren möchten, sollten Sie [die in der Dokumentation beschriebenen Schritte](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)ausführen.</span><span class="sxs-lookup"><span data-stu-id="5545e-215">To migrate your users from membership to the new identity tables, you should [follow the steps described in the documentation](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span> <span data-ttu-id="5545e-216">Nachdem Sie diese Schritte und das bereitgestellte Skript ausgeführt haben, müssen die Benutzer Ihr Kennwort bei der nächsten Anmeldung ändern.</span><span class="sxs-lookup"><span data-stu-id="5545e-216">After following these steps and the script provided, your users will need to change their password the next time they log in.</span></span>

<span data-ttu-id="5545e-217">Es ist möglich, Benutzer Kennwörter zu migrieren, aber der Prozess ist viel mehr beteiligt.</span><span class="sxs-lookup"><span data-stu-id="5545e-217">It is possible to migrate user passwords but the process is much more involved.</span></span> <span data-ttu-id="5545e-218">Wenn Sie möchten, dass Benutzer ihre Kenn Wörter im Rahmen des Migrations Vorgangs aktualisieren, und Sie dazu ermutigen, neue, eindeutige Kenn Wörter zu verwenden, ist es wahrscheinlich, dass die Gesamtsicherheit der Anwendung erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="5545e-218">Requiring users to update their passwords as part of the migration process, and encouraging them to use new, unique passwords, is likely to enhance the overall security of the application.</span></span>

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a><span data-ttu-id="5545e-219">Migrieren von Sicherheitseinstellungen von web.config zu Startup.cs</span><span class="sxs-lookup"><span data-stu-id="5545e-219">Migrating security settings from web.config to Startup.cs</span></span>

<span data-ttu-id="5545e-220">Wie bereits erwähnt, werden ASP.net-Mitgliedschafts-und Rollen Anbieter in der web.config Datei der Anwendung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5545e-220">As noted above, ASP.NET membership and role providers are configured in the application's web.config file.</span></span> <span data-ttu-id="5545e-221">Da ASP.net Core-apps nicht an IIS gebunden sind und ein separates System für die Konfiguration verwendet, müssen diese Einstellungen an anderer Stelle konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5545e-221">Since ASP.NET Core apps are not tied to IIS and use a separate system for configuration, these settings must be configured elsewhere.</span></span> <span data-ttu-id="5545e-222">Zum größten Teil wird ASP.net Core Identität in der-Datei konfiguriert `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="5545e-222">For the most part, ASP.NET Core Identity is configured in the `Startup.cs` file.</span></span> <span data-ttu-id="5545e-223">Öffnen Sie das zuvor erstellte Webprojekt (um das Schema der Identitäts Tabelle zu generieren), und überprüfen Sie die zugehörige `Startup.cs` Datei.</span><span class="sxs-lookup"><span data-stu-id="5545e-223">Open the web project that was created earlier (to generate the identity table schema) and review its `Startup.cs` file.</span></span>

<span data-ttu-id="5545e-224">Die Standardmethode für die Konfiguration von Methoden fügt Unterstützung für EF Core und Identität hinzu:</span><span class="sxs-lookup"><span data-stu-id="5545e-224">The default ConfigureServices method adds support for EF Core and Identity:</span></span>

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

<span data-ttu-id="5545e-225">Die `AddDefaultIdentity` -Erweiterungsmethode wird verwendet, um die Identität so zu konfigurieren, dass Sie die Standard- `ApplicationDbContext` und `IdentityUser` Frameworktypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5545e-225">The `AddDefaultIdentity` extension method is used to configure Identity to use the default `ApplicationDbContext` and the framework's `IdentityUser` type.</span></span> <span data-ttu-id="5545e-226">Wenn Sie einen benutzerdefinierten verwenden `IdentityUser` , achten Sie darauf, dass Sie den Typ hier angeben.</span><span class="sxs-lookup"><span data-stu-id="5545e-226">If you're using a custom `IdentityUser`, be sure to specify its type here.</span></span> <span data-ttu-id="5545e-227">Wenn diese Erweiterungs Methoden nicht in Ihrer Anwendung funktionieren, überprüfen Sie, ob Sie über die entsprechenden using-Anweisungen verfügen und dass Sie über die erforderlichen nuget-Paket Verweise verfügen.</span><span class="sxs-lookup"><span data-stu-id="5545e-227">If these extension methods aren't working in your application, check that you have the appropriate using statements and that you have the necessary NuGet package references.</span></span> <span data-ttu-id="5545e-228">Beispielsweise sollte Ihr Projekt eine Version der `Microsoft.AspNetCore.Identity.EntityFrameworkCore` -und-Pakete enthalten, auf die `Microsoft.AspNetCore.Identity.UI` verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5545e-228">For example, your project should have some version of the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` and `Microsoft.AspNetCore.Identity.UI` packages referenced.</span></span>

<span data-ttu-id="5545e-229">Außerdem `Startup.cs` sollte in die erforderliche Middleware für die Website angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5545e-229">Also in `Startup.cs` you should see the necessary middleware configured for the site.</span></span> <span data-ttu-id="5545e-230">`UseAuthentication`Und `UseAuthorization` sollten vor allem und am richtigen Speicherort eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="5545e-230">Specifically, `UseAuthentication` and `UseAuthorization` should be set up, and in the proper location.</span></span>

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

<span data-ttu-id="5545e-231">ASP.net Identity konfiguriert keinen anonymen oder rollenbasierten Zugriff auf Speicherorte von `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="5545e-231">ASP.NET Identity does not configure anonymous or role-based access to locations from `Startup.cs`.</span></span> <span data-ttu-id="5545e-232">Sie müssen ortsspezifische Autorisierungs Konfigurationsdaten zu Filtern in ASP.net Core migrieren.</span><span class="sxs-lookup"><span data-stu-id="5545e-232">You will need to migrate any location-specific authorization configuration data to filters in ASP.NET Core.</span></span> <span data-ttu-id="5545e-233">Notieren Sie sich, welche Ordner und Seiten solche Updates erfordern.</span><span class="sxs-lookup"><span data-stu-id="5545e-233">Make note of which folders and pages will require such updates.</span></span> <span data-ttu-id="5545e-234">Diese Änderungen werden im nächsten Abschnitt durchführen.</span><span class="sxs-lookup"><span data-stu-id="5545e-234">You will make these changes in the next section.</span></span>

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a><span data-ttu-id="5545e-235">Aktualisieren einzelner Seiten zur Verwendung ASP.net Core identitätsabstraktionen</span><span class="sxs-lookup"><span data-stu-id="5545e-235">Updating individual pages to use ASP.NET Core Identity abstractions</span></span>

<span data-ttu-id="5545e-236">Wenn Sie in Ihrer ASP.net Web Forms-Anwendung über web.config Einstellungen verfügen, um den Zugriff auf bestimmte Seiten oder Ordner auf anonyme Benutzer zu verweigern, migrieren Sie diese, indem Sie einfach das- `[Authorize]` Attribut zu diesen Seiten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5545e-236">In your ASP.NET Web Forms application, if you had web.config settings to deny access to certain pages or folders to anonymous users, you would migrate these by simply adding the `[Authorize]` attribute to such pages:</span></span>

```razor
@attribute [Authorize]
```

<span data-ttu-id="5545e-237">Wenn Sie den Zugriff mit Ausnahme der Benutzer, die zu einer bestimmten Rolle gehören, weiterhin verweigert haben, würden Sie diese auch migrieren, indem Sie ein Attribut hinzufügen, das eine Rolle angibt:</span><span class="sxs-lookup"><span data-stu-id="5545e-237">If you further had denied access except to those users belonging to a certain role, you would likewise migrate this by adding an attribute specifying a role:</span></span>

```razor
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="5545e-238">Beachten Sie, dass das- `[Authorize]` Attribut nur für `@page` Komponenten funktioniert, die über den Router erreicht werden Blazor .</span><span class="sxs-lookup"><span data-stu-id="5545e-238">Note that the `[Authorize]` attribute only works on `@page` components that are reached via the Blazor Router.</span></span> <span data-ttu-id="5545e-239">Das-Attribut funktioniert nicht mit untergeordneten Komponenten, die stattdessen verwenden sollten `AuthorizeView` .</span><span class="sxs-lookup"><span data-stu-id="5545e-239">The attribute does not work with child components, which should instead use `AuthorizeView`.</span></span>

<span data-ttu-id="5545e-240">Wenn Sie über Logik innerhalb des Seiten Markups verfügen, um zu bestimmen, ob Code für einen bestimmten Benutzer angezeigt werden soll, können Sie dies durch die `AuthorizeView` Komponente ersetzen.</span><span class="sxs-lookup"><span data-stu-id="5545e-240">If you have logic within page markup for determining whether to display some code to a certain user, you can replace this with the `AuthorizeView` component.</span></span> <span data-ttu-id="5545e-241">Die [Autorität "Autorität](/aspnet/core/blazor/security#authorizeview-component) anzeigen" zeigt selektiv die Benutzeroberfläche an, je nachdem, ob der Benutzer autorisiert ist, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5545e-241">The [AuthorizeView component](/aspnet/core/blazor/security#authorizeview-component) selectively displays UI depending on whether the user is authorized to see it.</span></span> <span data-ttu-id="5545e-242">Außerdem wird eine Variable verfügbar gemacht `context` , die für den Zugriff auf Benutzerinformationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5545e-242">It also exposes a `context` variable that can be used to access user information.</span></span>

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

<span data-ttu-id="5545e-243">Sie können auf den Authentifizierungs Status innerhalb der prozeduralen Logik zugreifen, indem Sie auf den Benutzer von einem `Task<AuthenticationState` mit dem-Attribut konfigurierten `[CascadingParameter]`</span><span class="sxs-lookup"><span data-stu-id="5545e-243">You can access authentication state within procedural logic by accessing the user from a `Task<AuthenticationState` configured with the `[CascadingParameter]` attribute.</span></span> <span data-ttu-id="5545e-244">Dadurch erhalten Sie Zugriff auf den Benutzer, mit dem Sie ermitteln können, ob Sie authentifiziert sind und ob Sie zu einer bestimmten Rolle gehören.</span><span class="sxs-lookup"><span data-stu-id="5545e-244">This will get you access to the user, which can let you determine if they are authenticated and if they belong to a particular role.</span></span> <span data-ttu-id="5545e-245">Wenn Sie eine Richtlinie prozedursch auswerten müssen, können Sie eine Instanz von einfügen `IAuthorizationService` und die- `AuthorizeAsync` Methode dafür aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5545e-245">If you need to evaluate a policy procedurally, you can inject an instance of the `IAuthorizationService` and calls the `AuthorizeAsync` method on it.</span></span> <span data-ttu-id="5545e-246">Der folgende Beispielcode veranschaulicht, wie Sie Benutzerinformationen erhalten und einem autorisierten Benutzer gestatten, eine durch die Richtlinie eingeschränkte Aufgabe auszuführen `content-editor` .</span><span class="sxs-lookup"><span data-stu-id="5545e-246">The following sample code demonstrates how to get user information and allow an authorized user to perform a task restricted by the `content-editor` policy.</span></span>

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

<span data-ttu-id="5545e-247">`AuthenticationState`Muss zunächst als kaskadierenden Wert eingerichtet werden, bevor er an einen kaskadierenden Parameter wie diesen gebunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="5545e-247">The `AuthenticationState` does first need to be setup as a cascading value before it can be bound to a cascading parameter like this.</span></span> <span data-ttu-id="5545e-248">Dies erfolgt in der Regel mithilfe der- `CascadingAuthenticationState` Komponente.</span><span class="sxs-lookup"><span data-stu-id="5545e-248">That's typically done using the `CascadingAuthenticationState` component.</span></span> <span data-ttu-id="5545e-249">Dies erfolgt in der Regel in `App.razor` :</span><span class="sxs-lookup"><span data-stu-id="5545e-249">This is typically done in `App.razor`:</span></span>

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

## <a name="summary"></a><span data-ttu-id="5545e-250">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="5545e-250">Summary</span></span>

<span data-ttu-id="5545e-251">Blazor verwendet das gleiche Sicherheitsmodell wie ASP.net Core, das ASP.net Core Identität ist.</span><span class="sxs-lookup"><span data-stu-id="5545e-251">Blazor uses the same security model as ASP.NET Core, which is ASP.NET Core Identity.</span></span> <span data-ttu-id="5545e-252">Die Migration von universellen Anbietern zur ASP.net Core Identität ist relativ unkompliziert, vorausgesetzt, dass nicht zu viele Anpassungen auf das ursprüngliche Datenschema angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5545e-252">Migrating from universal providers to ASP.NET Core Identity is relatively straightforward, assuming not too much customization was applied to the original data schema.</span></span> <span data-ttu-id="5545e-253">Nachdem die Daten migriert wurden, ist die Arbeit mit der Authentifizierung und Autorisierung in Blazor -apps gut dokumentiert, mit konfigurierbarer und Programm gesteuerter Unterstützung für die meisten Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="5545e-253">Once the data has been migrated, working with authentication and authorization in Blazor apps is well-documented, with configurable as well as programmatic support for most security requirements.</span></span>

## <a name="references"></a><span data-ttu-id="5545e-254">References</span><span class="sxs-lookup"><span data-stu-id="5545e-254">References</span></span>

- [<span data-ttu-id="5545e-255">Einführung in die Identität auf ASP.net Core</span><span class="sxs-lookup"><span data-stu-id="5545e-255">Introduction to Identity on ASP.NET Core</span></span>](/aspnet/core/security/authentication/identity)
- [<span data-ttu-id="5545e-256">Migrieren von der ASP.net-Mitgliedschafts Authentifizierung zu ASP.net Core 2,0-Identität</span><span class="sxs-lookup"><span data-stu-id="5545e-256">Migrate from ASP.NET Membership authentication to ASP.NET Core 2.0 Identity</span></span>](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [<span data-ttu-id="5545e-257">Migrieren von Authentifizierung und Identität zu ASP.net Core</span><span class="sxs-lookup"><span data-stu-id="5545e-257">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/core/migration/identity)
- [<span data-ttu-id="5545e-258">ASP.net Core Blazor Authentifizierung und Autorisierung</span><span class="sxs-lookup"><span data-stu-id="5545e-258">ASP.NET Core Blazor authentication and authorization</span></span>](/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
><span data-ttu-id="5545e-259">[Zurück](config.md)
>[Weiter](migration.md)</span><span class="sxs-lookup"><span data-stu-id="5545e-259">[Previous](config.md)
[Next](migration.md)</span></span>
