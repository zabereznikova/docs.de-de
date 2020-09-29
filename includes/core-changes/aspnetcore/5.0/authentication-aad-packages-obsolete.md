---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539475"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs und -Pakete als veraltet gekennzeichnet

In ASP.NET Core 2.1 wird die Integration in die Authentifizierung mit Azure Active Directory (Azure AD) und Azure Active Directory B2C (Azure AD B2C) durch die Pakete [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) und [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) ermöglicht. Die von diesen Paketen bereitgestellte Funktionalität basiert auf dem Azure AD 1.0- Endpunkt.

Ab ASP.NET Core 5.0 wird die Integration in die Authentifizierung mit Azure AD und Azure AD B2C durch das Paket [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) ermöglicht. Dieses Paket basiert auf der Microsoft Identity Platform, die zuvor als Azure AD 2.0-Endpunkt bekannt war. Folglich sind die alten APIs in den Paketen `Microsoft.AspNetCore.Authentication.AzureAD.UI` und `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` als veraltet markiert.

Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="old-behavior"></a>Altes Verhalten

Die APIs wurden nicht als veraltet markiert.

#### <a name="new-behavior"></a>Neues Verhalten

Die APIs sind als veraltet markiert.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Authentifizierungsfunktionalität von Azure AD und Azure AD B2C wurde zu den APIs der Microsoft Authentication Library (MSAL) migriert, die von `Microsoft.Identity.Web` bereitgestellt werden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Befolgen Sie die Anleitung zur API `Microsoft.Identity.Web` für [Web-Apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) und [Web-APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

* [Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
