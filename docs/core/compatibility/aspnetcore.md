---
title: Breaking Changes in ASP.NET Core
titleSuffix: ''
description: Liste der Breaking Changes in ASP.NET Core 3.0 und 3.1
ms.date: 11/03/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 40dfda77dd51ed46366ec6cd8f6598070e8ce846
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "96032440"
---
# <a name="aspnet-core-breaking-changes-for-versions-30-and-31"></a>Breaking Changes in ASP.NET Core für Version 3.0 und 3.1

ASP.NET Core stellt die von .NET Core verwendeten Web-App-Entwicklungsfeatures bereit.

Klicken Sie auf einen der folgenden Links, um Breaking Changes in einer bestimmten Version anzuzeigen:

* [ASP.NET Core 3.1](#aspnet-core-31)
* [ASP.NET Core 3.0](#aspnet-core-30)

Die folgenden Breaking Changes in ASP.NET Core 3.0 und 3.1 sind auf dieser Seite dokumentiert:

- [Veraltete Antifälschungs-, CORS-, Diagnose-, MVC- und Routing-APIs wurden entfernt](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Authentifizierung: Google+ ist veraltet](#authentication-google-deprecated-and-replaced)
- [Authentifizierung: HttpContext.Authentication-Eigenschaft wurde entfernt](#authentication-httpcontextauthentication-property-removed)
- [Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt](#authentication-newtonsoftjson-types-replaced)
- [Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync wurde geändert](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorisierung: AddAuthorization-Überladung wurde in andere Assembly verschoben](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorisierung: IAllowAnonymous wurde aus AuthorizationFilterContext.Filters entfernt](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt](#caching-compactonmemorypressure-property-removed)
- [Zwischenspeicherung: Microsoft.Extensions.Caching.SqlServer verwendet neues SqlClient-Paket](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Datenschutz: DataProtection.Blobs verwendet neue Azure Storage-APIs](#data-protection-dataprotectionblobs-uses-new-azure-storage-apis)
- [Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hosting: HTTPS-Umleitung für IIS-Out-of-Process-Apps aktiviert](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden ersetzt](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung](#http-browser-samesite-changes-impact-authentication)
- [HTTP: Erweiterbarkeit von DefaultHttpContext wurde entfernt](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: HeaderNames-Felder wurden in „static readonly“ (statisch schreibgeschützt) geändert](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: Änderungen an der Infrastruktur von Antworttexten](#http-response-body-infrastructure-changes)
- [HTTP: Einige Standardwerte für Cookie-SameSite wurden geändert](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: Synchrone E/A-Vorgänge wurden standardmäßig deaktiviert](#http-synchronous-io-disabled-in-all-servers)
- [Identität: AddDefaultUI-Methodenüberladung wurde entfernt](#identity-adddefaultui-method-overload-removed)
- [Identität: Bootstrap-Version der Benutzeroberfläche wurde geändert](#identity-default-bootstrap-version-of-ui-changed)
- [Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identität: SignInManager-Konstruktor akzeptiert neuen Parameter](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen](#identity-ui-uses-static-web-assets-feature)
- [Kestrel: Verbindungsadapter wurde entfernt](#kestrel-connection-adapters-removed)
- [Kestrel: Leere HTTPS-Assembly wurde entfernt](#kestrel-empty-https-assembly-removed)
- [Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: Transportabstraktionsebene wurde geändert](#kestrel-transport-abstractions-removed-and-made-public)
- [Lokalisierung: APIs wurden als veraltet markiert](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Protokollierung: DebugLogger-Klasse wurde als „internal“ deklariert](#logging-debuglogger-class-made-internal)
- [MVC: Async-Suffix wurde für Controlleraktion entfernt](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult wurde in Microsoft.AspNetCore.Mvc.Core verschoben](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: Vorkompilierungstool wurde als veraltet markiert](#mvc-precompilation-tool-deprecated)
- [MVC: Typen wurden in „internal“ geändert](#mvc-pubternal-types-changed-to-internal)
- [MVC: Web-API-Kompatibilitätsshim wurde entfernt](#mvc-web-api-compatibility-shim-removed)
- [Razor: RazorTemplateEngine-API wurde entfernt](#razor-razortemplateengine-api-removed)
- [Razor: Laufzeitkompilierung wurde in ein Paket verschoben](#razor-runtime-compilation-moved-to-a-package)
- [Sitzungszustand: Veraltete APIs wurden entfernt](#session-state-obsolete-apis-removed)
- [Freigegebenes Framework: Assembly aus Microsoft.AspNetCore.App wurde entfernt](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Freigegebenes Framework: Microsoft.AspNetCore.All wurde entfernt](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: HubConnection-Methoden wurden entfernt](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: HubConnectionContext-Konstruktoren wurden geändert](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: Name des JavaScript-Clientpakets wurde geändert](#signalr-javascript-client-package-name-changed)
- [SignalR: Veraltete APIs](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SPAs: Standard für Konsolenprotokollierungsfallback für SpaServices und NodeServices wurde geändert](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [SPAs: SpaServices und NodeServices wurden als veraltet markiert](#spas-spaservices-and-nodeservices-marked-obsolete)
- [Zielframework: .NET Framework nicht unterstützt](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-31"></a>ASP.NET Core 3.1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3.0

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

**_

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

_*_

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

_*_

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

_*_

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

_*_

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

_*_

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

_*_

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

_*_

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

_*_

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

_*_

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

_*_

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

_*_

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

_*_

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

_*_

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

_*_

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

_*_

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

_*_

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

_*_

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

_*_

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

_*_

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

_*_

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

_*_

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

_*_

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

_*_

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

_*_

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

_*_

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

_*_

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

_*_

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

_*_

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

_*_

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

_*_

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

_*_

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

_*_

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

_*_

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

_*_

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

_*_

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

_*_

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

_*_

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

_*_

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

_*_

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

_*_

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

_*_

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

_*_

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

_*_

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

_*_

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

_*_

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

_*_

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

_*_

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

_**
