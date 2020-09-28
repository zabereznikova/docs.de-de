---
title: Breaking Changes in ASP.NET Core
titleSuffix: ''
description: Listet die Breaking Changes in ASP.NET Core auf.
ms.date: 09/11/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 4c3167e9cad193b6a5a11be399e8be529df3be55
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539586"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="62a87-103">Breaking Changes in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="62a87-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="62a87-104">ASP.NET Core stellt die von .NET Core verwendeten Web-App-Entwicklungsfeatures bereit.</span><span class="sxs-lookup"><span data-stu-id="62a87-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="62a87-105">Klicken Sie auf einen der folgenden Links, um Breaking Changes in einer bestimmten Version anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="62a87-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="62a87-106">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="62a87-106">ASP.NET Core 5.0</span></span>](#aspnet-core-50)
* [<span data-ttu-id="62a87-107">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="62a87-107">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="62a87-108">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="62a87-108">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="62a87-109">Die folgenden Breaking Changes in ASP.NET Core 3.0, 3.1 und 5.0 sind auf dieser Seite dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="62a87-109">The following breaking changes in ASP.NET Core 3.0, 3.1, and 5.0 are documented on this page:</span></span>

- [<span data-ttu-id="62a87-110">Veraltete Antifälschungs-, CORS-, Diagnose-, MVC- und Routing-APIs wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-110">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="62a87-111">Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs sowie -Pakete wurden als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="62a87-111">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>](#authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete)
- [<span data-ttu-id="62a87-112">Authentifizierung: Google+ ist veraltet</span><span class="sxs-lookup"><span data-stu-id="62a87-112">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="62a87-113">Authentifizierung: HttpContext.Authentication-Eigenschaft wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-113">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="62a87-114">Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt</span><span class="sxs-lookup"><span data-stu-id="62a87-114">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="62a87-115">Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-115">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="62a87-116">Autorisierung: AddAuthorization-Überladung wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="62a87-116">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="62a87-117">Autorisierung: IAllowAnonymous wurde aus AuthorizationFilterContext.Filters entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-117">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="62a87-118">Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode</span><span class="sxs-lookup"><span data-stu-id="62a87-118">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="62a87-119">Autorisierung: Die Ressource im Endpunktrouting ist HttpContext</span><span class="sxs-lookup"><span data-stu-id="62a87-119">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="62a87-120">Azure: Azure-Integrationspakete mit Präfix „Microsoft“ entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-120">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="62a87-121">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="62a87-121">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [<span data-ttu-id="62a87-122">Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-122">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="62a87-123">Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="62a87-123">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>](#blazor-rendertreeframe-readonly-public-fields-have-become-properties)
- [<span data-ttu-id="62a87-124">Blazor: Das Zielframework von NuGet-Paketen wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-124">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="62a87-125">Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-125">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="62a87-126">Zwischenspeicherung: Microsoft.Extensions.Caching.SqlServer verwendet neues SqlClient-Paket</span><span class="sxs-lookup"><span data-stu-id="62a87-126">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="62a87-127">Zwischenspeicherung: „pubternal“-Typen wurden in ResponseCaching in „internal“-Typen geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-127">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="62a87-128">Datenschutz: DataProtection.AzureStorage verwendet neue Azure Storage-APIs</span><span class="sxs-lookup"><span data-stu-id="62a87-128">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="62a87-129">Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="62a87-129">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="62a87-130">Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-130">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="62a87-131">Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein</span><span class="sxs-lookup"><span data-stu-id="62a87-131">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="62a87-132">Hosting: HTTPS-Umleitung für IIS-Out-of-Process-Apps aktiviert</span><span class="sxs-lookup"><span data-stu-id="62a87-132">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="62a87-133">Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden ersetzt</span><span class="sxs-lookup"><span data-stu-id="62a87-133">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="62a87-134">Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-134">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="62a87-135">HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt</span><span class="sxs-lookup"><span data-stu-id="62a87-135">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="62a87-136">HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="62a87-136">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="62a87-137">HTTP: Erweiterbarkeit von DefaultHttpContext wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-137">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="62a87-138">HTTP: HeaderNames-Felder wurden in „static readonly“ (statisch schreibgeschützt) geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-138">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="62a87-139">HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes</span><span class="sxs-lookup"><span data-stu-id="62a87-139">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="62a87-140">HTTP: Änderungen an der Infrastruktur von Antworttexten</span><span class="sxs-lookup"><span data-stu-id="62a87-140">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="62a87-141">HTTP: Einige Standardwerte für Cookie-SameSite wurden geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-141">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="62a87-142">HTTP: Synchrone E/A-Vorgänge wurden standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="62a87-142">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="62a87-143">HttpSys: Neuverhandlung von Clientzertifikaten standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="62a87-143">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="62a87-144">Identität: AddDefaultUI-Methodenüberladung wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-144">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="62a87-145">Identität: Bootstrap-Version der Benutzeroberfläche wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-145">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="62a87-146">Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus</span><span class="sxs-lookup"><span data-stu-id="62a87-146">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="62a87-147">Identität: SignInManager-Konstruktor akzeptiert neuen Parameter</span><span class="sxs-lookup"><span data-stu-id="62a87-147">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="62a87-148">Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen</span><span class="sxs-lookup"><span data-stu-id="62a87-148">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="62a87-149">IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten</span><span class="sxs-lookup"><span data-stu-id="62a87-149">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="62a87-150">Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt</span><span class="sxs-lookup"><span data-stu-id="62a87-150">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="62a87-151">Kestrel: Verbindungsadapter wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-151">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="62a87-152">Kestrel: Standardmäßig unterstützte TLS-Protokollversionen geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-152">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="62a87-153">Kestrel: Leere HTTPS-Assembly wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-153">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="62a87-154">Kestrel: HTTP/2 wird bei inkompatiblen Windows-Versionen über TLS deaktiviert</span><span class="sxs-lookup"><span data-stu-id="62a87-154">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="62a87-155">Kestrel: Markierung von libuv-Transport als veraltet</span><span class="sxs-lookup"><span data-stu-id="62a87-155">Kestrel: Libuv transport marked as obsolete</span></span>](#kestrel-libuv-transport-marked-as-obsolete)
- [<span data-ttu-id="62a87-156">Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben</span><span class="sxs-lookup"><span data-stu-id="62a87-156">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="62a87-157">Kestrel: Transportabstraktionsebene wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-157">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="62a87-158">Lokalisierung: APIs wurden als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="62a87-158">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="62a87-159">Lokalisierung: „Pubternal“-APIs entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-159">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="62a87-160">Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-160">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="62a87-161">Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-161">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="62a87-162">Protokollierung: DebugLogger-Klasse wurde als „internal“ deklariert</span><span class="sxs-lookup"><span data-stu-id="62a87-162">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="62a87-163">Middleware: Datenbankfehlerseite als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="62a87-163">Middleware: Database error page marked as obsolete</span></span>](#middleware-database-error-page-marked-as-obsolete)
- [<span data-ttu-id="62a87-164">Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde</span><span class="sxs-lookup"><span data-stu-id="62a87-164">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [<span data-ttu-id="62a87-165">MVC: Async-Suffix wurde für Controlleraktion entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-165">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="62a87-166">MVC: JsonResult wurde in Microsoft.AspNetCore.Mvc.Core verschoben</span><span class="sxs-lookup"><span data-stu-id="62a87-166">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="62a87-167">MVC: Vorkompilierungstool wurde als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="62a87-167">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="62a87-168">MVC: Typen wurden in „internal“ geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-168">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="62a87-169">MVC: Web-API-Kompatibilitätsshim wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-169">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="62a87-170">Razor: RazorTemplateEngine-API wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-170">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="62a87-171">Razor: Laufzeitkompilierung wurde in ein Paket verschoben</span><span class="sxs-lookup"><span data-stu-id="62a87-171">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="62a87-172">Sicherheit: Die Codierung für Cookienamen wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-172">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="62a87-173">Sicherheit: Die Versionen des IdentityModel-NuGet-Pakets wurden aktualisiert</span><span class="sxs-lookup"><span data-stu-id="62a87-173">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="62a87-174">Sitzungszustand: Veraltete APIs wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-174">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="62a87-175">Freigegebenes Framework: Assembly aus Microsoft.AspNetCore.App wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-175">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="62a87-176">Freigegebenes Framework: Microsoft.AspNetCore.All wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-176">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="62a87-177">SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt</span><span class="sxs-lookup"><span data-stu-id="62a87-177">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="62a87-178">SignalR: HubConnection-Methoden wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-178">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="62a87-179">SignalR: HubConnectionContext-Konstruktoren wurden geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-179">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="62a87-180">SignalR: Name des JavaScript-Clientpakets wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-180">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="62a87-181">SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben</span><span class="sxs-lookup"><span data-stu-id="62a87-181">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="62a87-182">SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-182">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="62a87-183">SignalR: Veraltete APIs</span><span class="sxs-lookup"><span data-stu-id="62a87-183">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="62a87-184">SignalR: UseSignalR- und UseConnections-Methoden entfernt</span><span class="sxs-lookup"><span data-stu-id="62a87-184">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="62a87-185">SPAs: Standard für Konsolenprotokollierungsfallback für SpaServices und NodeServices wurde geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-185">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="62a87-186">SPAs: SpaServices und NodeServices wurden als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="62a87-186">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="62a87-187">Statische Dateien: CSV-Inhaltstyp in standardkonform geändert</span><span class="sxs-lookup"><span data-stu-id="62a87-187">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="62a87-188">Zielframework: .NET Framework nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="62a87-188">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="62a87-189">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="62a87-189">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete](~/includes/core-changes/aspnetcore/5.0/authentication-aad-packages-obsolete.md)]

***

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

***

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

***

[!INCLUDE[Blazor: RenderTreeFrame readonly public fields have become properties](~/includes/core-changes/aspnetcore/5.0/blazor-rendertreeframe-fields-become-properties.md)]

***

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

***

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

***

[!INCLUDE[Kestrel: Libuv transport marked as obsolete](~/includes/core-changes/aspnetcore/5.0/kestrel-libuv-transport-obsolete.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[Middleware: Database error page marked as obsolete](~/includes/core-changes/aspnetcore/5.0/middleware-database-error-page-obsolete.md)]

***

[!INCLUDE[Middleware: Exception Handler Middleware throws original exception if handler not found](~/includes/core-changes/aspnetcore/5.0/middleware-exception-handler-throws-original-exception.md)]

***

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

***

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="62a87-190">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="62a87-190">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="62a87-191">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="62a87-191">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
