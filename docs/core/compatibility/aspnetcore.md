---
title: Breaking Changes in ASP.NET Core
titleSuffix: ''
description: Listet die Breaking Changes in ASP.NET Core auf.
ms.date: 10/06/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 37a366e30f7dc25a5da430de777755b8c9f6dd38
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804945"
---
# <a name="aspnet-core-breaking-changes"></a>Breaking Changes in ASP.NET Core

ASP.NET Core stellt die von .NET Core verwendeten Web-App-Entwicklungsfeatures bereit.

Klicken Sie auf einen der folgenden Links, um Breaking Changes in einer bestimmten Version anzuzeigen:

* [ASP.NET Core 5.0](#aspnet-core-50)
* [ASP.NET Core 3.1](#aspnet-core-31)
* [ASP.NET Core 3.0](#aspnet-core-30)

Die folgenden Breaking Changes in ASP.NET Core 3.0, 3.1 und 5.0 sind auf dieser Seite dokumentiert:

- [Veraltete Antifälschungs-, CORS-, Diagnose-, MVC- und Routing-APIs wurden entfernt](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs sowie -Pakete wurden als veraltet gekennzeichnet.](#authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete)
- [Authentifizierung: Google+ ist veraltet](#authentication-google-deprecated-and-replaced)
- [Authentifizierung: HttpContext.Authentication-Eigenschaft wurde entfernt](#authentication-httpcontextauthentication-property-removed)
- [Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt](#authentication-newtonsoftjson-types-replaced)
- [Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync wurde geändert](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorisierung: AddAuthorization-Überladung wurde in andere Assembly verschoben](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorisierung: IAllowAnonymous wurde aus AuthorizationFilterContext.Filters entfernt](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Autorisierung: Die Ressource im Endpunktrouting ist HttpContext](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [Azure: Azure-Integrationspakete mit Präfix „Microsoft“ entfernt](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert](#blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal)
- [Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben](#blazor-protectedbrowserstorage-feature-moved-to-shared-framework)
- [Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften.](#blazor-rendertreeframe-readonly-public-fields-have-become-properties)
- [Blazor: Das Zielframework von NuGet-Paketen wurde geändert](#blazor-target-framework-of-nuget-packages-changed)
- [Blazor: Aktualisierte Browserunterstützung](#blazor-updated-browser-support)
- [Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt](#caching-compactonmemorypressure-property-removed)
- [Zwischenspeicherung: Microsoft.Extensions.Caching.SqlServer verwendet neues SqlClient-Paket](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Zwischenspeicherung: „pubternal“-Typen wurden in ResponseCaching in „internal“-Typen geändert](#caching-responsecaching-pubternal-types-changed-to-internal)
- [Datenschutz: DataProtection.AzureStorage verwendet neue Azure Storage-APIs](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hosting: Generischer Host schränkt Startup-Konstruktorinjektion ein](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hosting: HTTPS-Umleitung für IIS-Out-of-Process-Apps aktiviert](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden ersetzt](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung](#http-browser-samesite-changes-impact-authentication)
- [HTTP: Erweiterbarkeit von DefaultHttpContext wurde entfernt](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: HeaderNames-Felder wurden in „static readonly“ (statisch schreibgeschützt) geändert](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [HTTP: Änderungen an der Infrastruktur von Antworttexten](#http-response-body-infrastructure-changes)
- [HTTP: Einige Standardwerte für Cookie-SameSite wurden geändert](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: Synchrone E/A-Vorgänge wurden standardmäßig deaktiviert](#http-synchronous-io-disabled-in-all-servers)
- [HttpSys: Neuverhandlung von Clientzertifikaten standardmäßig deaktiviert](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [Identität: AddDefaultUI-Methodenüberladung wurde entfernt](#identity-adddefaultui-method-overload-removed)
- [Identität: Bootstrap-Version der Benutzeroberfläche wurde geändert](#identity-default-bootstrap-version-of-ui-changed)
- [Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identität: SignInManager-Konstruktor akzeptiert neuen Parameter](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen](#identity-ui-uses-static-web-assets-feature)
- [IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [Kestrel: Verbindungsadapter wurde entfernt](#kestrel-connection-adapters-removed)
- [Kestrel: Standardmäßig unterstützte TLS-Protokollversionen geändert](#kestrel-default-supported-tls-protocol-versions-changed)
- [Kestrel: Leere HTTPS-Assembly wurde entfernt](#kestrel-empty-https-assembly-removed)
- [Kestrel: HTTP/2 wird bei inkompatiblen Windows-Versionen über TLS deaktiviert](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [Kestrel: Markierung von libuv-Transport als veraltet](#kestrel-libuv-transport-marked-as-obsolete)
- [Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: Transportabstraktionsebene wurde geändert](#kestrel-transport-abstractions-removed-and-made-public)
- [Lokalisierung: APIs wurden als veraltet markiert](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Lokalisierung: „Pubternal“-APIs entfernt](#localization-pubternal-apis-removed)
- [Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [Protokollierung: DebugLogger-Klasse wurde als „internal“ deklariert](#logging-debuglogger-class-made-internal)
- [Middleware: Datenbankfehlerseite als veraltet markiert](#middleware-database-error-page-marked-as-obsolete)
- [Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [MVC: Async-Suffix wurde für Controlleraktion entfernt](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult wurde in Microsoft.AspNetCore.Mvc.Core verschoben](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: Die ObjectModelValidator-Klasse ruft eine neue Überladung von ValidationVisitor.Validate auf.](#mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate)
- [MVC: Vorkompilierungstool wurde als veraltet markiert](#mvc-precompilation-tool-deprecated)
- [MVC: Typen wurden in „internal“ geändert](#mvc-pubternal-types-changed-to-internal)
- [MVC: Web-API-Kompatibilitätsshim wurde entfernt](#mvc-web-api-compatibility-shim-removed)
- [Razor: RazorTemplateEngine-API wurde entfernt](#razor-razortemplateengine-api-removed)
- [Razor: Laufzeitkompilierung wurde in ein Paket verschoben](#razor-runtime-compilation-moved-to-a-package)
- [Sicherheit: Die Codierung für Cookienamen wurde entfernt](#security-cookie-name-encoding-removed)
- [Sicherheit: Die Versionen des IdentityModel-NuGet-Pakets wurden aktualisiert](#security-identitymodel-nuget-package-versions-updated)
- [Sitzungszustand: Veraltete APIs wurden entfernt](#session-state-obsolete-apis-removed)
- [Freigegebenes Framework: Assembly aus Microsoft.AspNetCore.App wurde entfernt](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Freigegebenes Framework: Microsoft.AspNetCore.All wurde entfernt](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: HubConnection-Methoden wurden entfernt](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: HubConnectionContext-Konstruktoren wurden geändert](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: Name des JavaScript-Clientpakets wurde geändert](#signalr-javascript-client-package-name-changed)
- [SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [SignalR: Optionstyp für das MessagePack-Hubprotokoll geändert](#signalr-messagepack-hub-protocol-options-type-changed)
- [SignalR: Veraltete APIs](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SignalR: UseSignalR- und UseConnections-Methoden entfernt](#signalr-usesignalr-and-useconnections-methods-removed)
- [SPAs: Standard für Konsolenprotokollierungsfallback für SpaServices und NodeServices wurde geändert](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [SPAs: SpaServices und NodeServices wurden als veraltet markiert](#spas-spaservices-and-nodeservices-marked-obsolete)
- [Statische Dateien: CSV-Inhaltstyp in standardkonform geändert](#static-files-csv-content-type-changed-to-standards-compliant)
- [System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly)
- [Zielframework: .NET Framework nicht unterstützt](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a>ASP.NET Core 5.0

[!INCLUDE[Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete](~/includes/core-changes/aspnetcore/5.0/authentication-aad-packages-obsolete.md)]

***

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

***

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Serialization: BinaryFormatter serialization obsolete](~/includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

***

[!INCLUDE[Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal](~/includes/core-changes/aspnetcore/5.0/blazor-jsobjectreference-to-internal.md)]

***

[!INCLUDE[Blazor: ProtectedBrowserStorage feature moved to shared framework](~/includes/core-changes/aspnetcore/5.0/blazor-protectedbrowserstorage-moved.md)]

***

[!INCLUDE[Blazor: RenderTreeFrame readonly public fields have become properties](~/includes/core-changes/aspnetcore/5.0/blazor-rendertreeframe-fields-become-properties.md)]

***

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

***

[!INCLUDE[Blazor: Updated browser support](~/includes/core-changes/aspnetcore/5.0/blazor-browser-support-updated.md)]

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

[!INCLUDE[MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate](~/includes/core-changes/aspnetcore/5.0/mvc-objectmodelvalidator-calls-new-overload.md)]

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

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a>ASP.NET Core 3.1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3.0

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
