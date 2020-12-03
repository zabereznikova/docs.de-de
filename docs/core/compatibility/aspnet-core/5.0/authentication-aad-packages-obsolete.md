---
title: 'Breaking Change: Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs und -Pakete als veraltet gekennzeichnet'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs und -Pakete als veraltet gekennzeichnet'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c977ba4d6e34fc5f11133bdd1446a94d54efcb63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759539"
---
# <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="6a04a-103">Authentifizierung: AzureAD.UI- und AzureADB2C.UI-APIs und -Pakete als veraltet gekennzeichnet</span><span class="sxs-lookup"><span data-stu-id="6a04a-103">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="6a04a-104">In ASP.NET Core 2.1 wird die Integration in die Authentifizierung mit Azure Active Directory (Azure AD) und Azure Active Directory B2C (Azure AD B2C) durch die Pakete [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) und [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6a04a-104">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="6a04a-105">Die von diesen Paketen bereitgestellte Funktionalität basiert auf dem Azure AD 1.0- Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="6a04a-105">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="6a04a-106">Ab ASP.NET Core 5.0 wird die Integration in die Authentifizierung mit Azure AD und Azure AD B2C durch das Paket [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6a04a-106">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="6a04a-107">Dieses Paket basiert auf der Microsoft Identity Platform, die zuvor als Azure AD 2.0-Endpunkt bekannt war.</span><span class="sxs-lookup"><span data-stu-id="6a04a-107">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="6a04a-108">Folglich sind die alten APIs in den Paketen `Microsoft.AspNetCore.Authentication.AzureAD.UI` und `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="6a04a-108">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="6a04a-109">Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span><span class="sxs-lookup"><span data-stu-id="6a04a-109">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6a04a-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6a04a-110">Version introduced</span></span>

<span data-ttu-id="6a04a-111">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="6a04a-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6a04a-112">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="6a04a-112">Old behavior</span></span>

<span data-ttu-id="6a04a-113">Die APIs wurden nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="6a04a-113">The APIs weren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6a04a-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="6a04a-114">New behavior</span></span>

<span data-ttu-id="6a04a-115">Die APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="6a04a-115">The APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6a04a-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="6a04a-116">Reason for change</span></span>

<span data-ttu-id="6a04a-117">Die Authentifizierungsfunktionalität von Azure AD und Azure AD B2C wurde zu den APIs der Microsoft Authentication Library (MSAL) migriert, die von `Microsoft.Identity.Web` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a04a-117">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6a04a-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="6a04a-118">Recommended action</span></span>

<span data-ttu-id="6a04a-119">Befolgen Sie die Anleitung zur API `Microsoft.Identity.Web` für [Web-Apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) und [Web-APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span><span class="sxs-lookup"><span data-stu-id="6a04a-119">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6a04a-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6a04a-120">Affected APIs</span></span>

* [<span data-ttu-id="6a04a-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="6a04a-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="6a04a-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="6a04a-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="6a04a-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="6a04a-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="6a04a-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="6a04a-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="6a04a-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="6a04a-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="6a04a-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="6a04a-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
