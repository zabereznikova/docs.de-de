---
title: Breaking Changes in ASP.NET Core
titleSuffix: ''
description: Listet die Breaking Changes in ASP.NET Core auf.
ms.date: 06/11/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: a6ddf97f907a1cba57e51d6fd516d1f94272f725
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803275"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="b7c65-103">Breaking Changes in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c65-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="b7c65-104">ASP.NET Core stellt die von .NET Core verwendeten Web-App-Entwicklungsfeatures bereit.</span><span class="sxs-lookup"><span data-stu-id="b7c65-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="b7c65-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="b7c65-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="b7c65-106">Veraltete Antifälschungs-, CORS-, Diagnose-, MVC- und Routing-APIs wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="b7c65-107">Authentifizierung: Google+ ist veraltet</span><span class="sxs-lookup"><span data-stu-id="b7c65-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="b7c65-108">Authentifizierung: HttpContext.Authentication-Eigenschaft wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="b7c65-109">Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt</span><span class="sxs-lookup"><span data-stu-id="b7c65-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="b7c65-110">Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync wurde geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="b7c65-111">Autorisierung: AddAuthorization-Überladung wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="b7c65-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="b7c65-112">Autorisierung: IAllowAnonymous wurde aus AuthorizationFilterContext.Filters entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="b7c65-113">Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode</span><span class="sxs-lookup"><span data-stu-id="b7c65-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="b7c65-114">Azure: Azure-Integrationspakete mit Präfix „Microsoft“ entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="b7c65-115">Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-115">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="b7c65-116">Zwischenspeicherung: Microsoft.Extensions.Caching.SqlServer verwendet neues SqlClient-Paket</span><span class="sxs-lookup"><span data-stu-id="b7c65-116">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="b7c65-117">Zwischenspeicherung: „pubternal“-Typen wurden in ResponseCaching in „internal“-Typen geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-117">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b7c65-118">Datenschutz: DataProtection.AzureStorage verwendet neue Azure Storage-APIs</span><span class="sxs-lookup"><span data-stu-id="b7c65-118">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="b7c65-119">Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="b7c65-119">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="b7c65-120">Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-120">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="b7c65-121">Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein</span><span class="sxs-lookup"><span data-stu-id="b7c65-121">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="b7c65-122">Hosting: HTTPS-Umleitung für IIS-Out-of-Process-Apps aktiviert</span><span class="sxs-lookup"><span data-stu-id="b7c65-122">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="b7c65-123">Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden ersetzt</span><span class="sxs-lookup"><span data-stu-id="b7c65-123">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b7c65-124">Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-124">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="b7c65-125">HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt</span><span class="sxs-lookup"><span data-stu-id="b7c65-125">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b7c65-126">HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b7c65-126">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="b7c65-127">HTTP: Erweiterbarkeit von DefaultHttpContext wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-127">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="b7c65-128">HTTP: HeaderNames-Felder wurden in „static readonly“ (statisch schreibgeschützt) geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-128">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="b7c65-129">HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes</span><span class="sxs-lookup"><span data-stu-id="b7c65-129">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="b7c65-130">HTTP: Änderungen an der Infrastruktur von Antworttexten</span><span class="sxs-lookup"><span data-stu-id="b7c65-130">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="b7c65-131">HTTP: Einige Standardwerte für Cookie-SameSite wurden geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-131">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="b7c65-132">HTTP: Synchrone E/A-Vorgänge wurden standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="b7c65-132">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="b7c65-133">Identität: AddDefaultUI-Methodenüberladung wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-133">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="b7c65-134">Identität: Bootstrap-Version der Benutzeroberfläche wurde geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-134">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="b7c65-135">Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus</span><span class="sxs-lookup"><span data-stu-id="b7c65-135">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="b7c65-136">Identität: SignInManager-Konstruktor akzeptiert neuen Parameter</span><span class="sxs-lookup"><span data-stu-id="b7c65-136">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="b7c65-137">Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen</span><span class="sxs-lookup"><span data-stu-id="b7c65-137">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="b7c65-138">Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt</span><span class="sxs-lookup"><span data-stu-id="b7c65-138">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="b7c65-139">Kestrel: Verbindungsadapter wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-139">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="b7c65-140">Kestrel: Standardmäßig unterstützte TLS-Protokollversionen geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-140">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="b7c65-141">Kestrel: Leere HTTPS-Assembly wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-141">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="b7c65-142">Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben</span><span class="sxs-lookup"><span data-stu-id="b7c65-142">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="b7c65-143">Kestrel: Transportabstraktionsebene wurde geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-143">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="b7c65-144">Lokalisierung: APIs wurden als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="b7c65-144">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="b7c65-145">Lokalisierung: „Pubternal“-APIs entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-145">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="b7c65-146">Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-146">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="b7c65-147">Protokollierung: DebugLogger-Klasse wurde als „internal“ deklariert</span><span class="sxs-lookup"><span data-stu-id="b7c65-147">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="b7c65-148">MVC: Async-Suffix wurde für Controlleraktion entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-148">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="b7c65-149">MVC: JsonResult wurde in Microsoft.AspNetCore.Mvc.Core verschoben</span><span class="sxs-lookup"><span data-stu-id="b7c65-149">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="b7c65-150">MVC: Vorkompilierungstool wurde als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="b7c65-150">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="b7c65-151">MVC: Typen wurden in „internal“ geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-151">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b7c65-152">MVC: Web-API-Kompatibilitätsshim wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-152">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="b7c65-153">Razor: Laufzeitkompilierung wurde in ein Paket verschoben</span><span class="sxs-lookup"><span data-stu-id="b7c65-153">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="b7c65-154">Sitzungszustand: Veraltete APIs wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-154">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="b7c65-155">Freigegebenes Framework: Assembly aus Microsoft.AspNetCore.App wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-155">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="b7c65-156">Freigegebenes Framework: Microsoft.AspNetCore.All wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-156">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="b7c65-157">SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt</span><span class="sxs-lookup"><span data-stu-id="b7c65-157">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="b7c65-158">SignalR: HubConnection-Methoden wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-158">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="b7c65-159">SignalR: HubConnectionContext-Konstruktoren wurden geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-159">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="b7c65-160">SignalR: Name des JavaScript-Clientpakets wurde geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-160">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="b7c65-161">SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben</span><span class="sxs-lookup"><span data-stu-id="b7c65-161">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="b7c65-162">SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-162">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="b7c65-163">SignalR: Veraltete APIs</span><span class="sxs-lookup"><span data-stu-id="b7c65-163">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="b7c65-164">SignalR: UseSignalR- und UseConnections-Methoden entfernt</span><span class="sxs-lookup"><span data-stu-id="b7c65-164">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="b7c65-165">SPAs: Standard für Konsolenprotokollierungsfallback für SpaServices und NodeServices wurde geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-165">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="b7c65-166">SPAs: SpaServices und NodeServices wurden als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="b7c65-166">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="b7c65-167">Statische Dateien: CSV-Inhaltstyp in standardkonform geändert</span><span class="sxs-lookup"><span data-stu-id="b7c65-167">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="b7c65-168">Zielframework: .NET Framework nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b7c65-168">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="b7c65-169">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="b7c65-169">ASP.NET Core 5.0</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="b7c65-170">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b7c65-170">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="b7c65-171">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b7c65-171">ASP.NET Core 3.0</span></span>

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
