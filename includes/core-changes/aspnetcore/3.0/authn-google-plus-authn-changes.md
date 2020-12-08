---
ms.openlocfilehash: 14d80f25c34465caa6dec10e5704fe0a3cbccc71
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477590"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="3a48a-101">Authentifizierung: Google+ wurde als veraltet markiert und ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3a48a-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="3a48a-102">Google hat ab 28. Januar 2019 damit begonnen, die Google+-Anmeldung für Apps [einzustellen](https://developers.google.com/+/api-shutdown).</span><span class="sxs-lookup"><span data-stu-id="3a48a-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3a48a-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3a48a-103">Change description</span></span>

<span data-ttu-id="3a48a-104">ASP.NET 4.x und ASP.NET Core verwendeten die Google+-Anmelde-APIs zum Authentifizieren von Google-Benutzerkonten in Web-Apps.</span><span class="sxs-lookup"><span data-stu-id="3a48a-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="3a48a-105">Die betroffenen NuGet-Pakete sind [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) für ASP.NET Core und [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) für `Microsoft.Owin` mit ASP.NET Web Forms und MVC.</span><span class="sxs-lookup"><span data-stu-id="3a48a-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="3a48a-106">Die Ersetzungs-APIs von Google nutzen eine andere Datenquelle und ein anderes Format.</span><span class="sxs-lookup"><span data-stu-id="3a48a-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="3a48a-107">Mit den unten aufgeführten Entschärfungen und Lösungen wird auf diese strukturellen Änderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="3a48a-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="3a48a-108">Apps sollten überprüfen, ob die Daten selbst weiterhin die Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3a48a-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="3a48a-109">Beispielsweise können Namen, E-Mail-Adressen, Profilverknüpfungen und Profilfotos etwas andere Werte als zuvor bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3a48a-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3a48a-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3a48a-110">Version introduced</span></span>

<span data-ttu-id="3a48a-111">Alle Versionen.</span><span class="sxs-lookup"><span data-stu-id="3a48a-111">All versions.</span></span> <span data-ttu-id="3a48a-112">Diese Änderung ist extern von ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a48a-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3a48a-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3a48a-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="3a48a-114">Owin mit ASP.NET Web Forms und MVC</span><span class="sxs-lookup"><span data-stu-id="3a48a-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="3a48a-115">Für `Microsoft.Owin` 3.1.0 und höher finden Sie [hier](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) eine vorübergehende Entschärfung.</span><span class="sxs-lookup"><span data-stu-id="3a48a-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="3a48a-116">Apps sollten Tests mit der Entschärfung durchführen, um Änderungen am Datenformat zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3a48a-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="3a48a-117">Es gibt Pläne, `Microsoft.Owin` 4.0.1 mit einer Korrektur zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3a48a-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="3a48a-118">Apps, die eine frühere Version verwenden, sollten auf Version 4.0.1 aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a48a-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="3a48a-119">ASP.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3a48a-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="3a48a-120">Die Entschärfung in [Owin mit ASP.NET Web Forms und MVC](#owin-with-aspnet-web-forms-and-mvc) kann an ASP.NET Core 1.x angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3a48a-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="3a48a-121">NuGet-Paketpatches sind nicht geplant, da Version 1.x das [Ende des Lebenszyklus](https://dotnet.microsoft.com/platform/support-policy) erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="3a48a-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="3a48a-122">ASP.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3a48a-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="3a48a-123">Ersetzen Sie für `Microsoft.AspNetCore.Authentication.Google` Version 2.x den vorhandenen Aufruf von `AddGoogle` in `Startup.ConfigureServices` durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3a48a-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

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

<span data-ttu-id="3a48a-124">Die Februar-Patches 2.1 und 2.2 enthalten die vorherige Neukonfiguration als neuen Standard.</span><span class="sxs-lookup"><span data-stu-id="3a48a-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="3a48a-125">Es ist kein Patch für ASP.NET Core 2.0 geplant, da diese Version das [Ende des Lebenszyklus](https://dotnet.microsoft.com/platform/support-policy) erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="3a48a-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="3a48a-126">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3a48a-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="3a48a-127">Die für ASP.NET Core 2.x angegebene Entschärfung kann auch für ASP.NET Core 3.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a48a-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="3a48a-128">In den nächsten Vorschauversionen für 3.0 wird das Paket `Microsoft.AspNetCore.Authentication.Google` möglicherweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a48a-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="3a48a-129">Benutzer würden stattdessen an `Microsoft.AspNetCore.Authentication.OpenIdConnect` weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3a48a-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="3a48a-130">Im folgenden Code wird das Ersetzen von `AddGoogle` durch `AddOpenIdConnect` in `Startup.ConfigureServices` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3a48a-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="3a48a-131">Diese Ersetzung kann mit ASP.NET Core 2.0 und höher verwendet und bei Bedarf für ASP.NET Core 1.x angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3a48a-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/signin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a><span data-ttu-id="3a48a-132">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3a48a-132">Category</span></span>

<span data-ttu-id="3a48a-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a48a-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a48a-134">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3a48a-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
