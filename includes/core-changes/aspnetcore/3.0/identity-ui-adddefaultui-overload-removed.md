---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637196"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="19f0d-101">Identität: AddDefaultUI-Methodenüberladung wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="19f0d-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="19f0d-102">Ab ASP.NET Core 3.0 ist die Methodenüberladung [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="19f0d-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="19f0d-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="19f0d-103">Version introduced</span></span>

<span data-ttu-id="19f0d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="19f0d-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="19f0d-105">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="19f0d-105">Reason for change</span></span>

<span data-ttu-id="19f0d-106">Diese Änderung wurde aufgrund der Einführung der Funktion für statische Webressourcen notwendig.</span><span class="sxs-lookup"><span data-stu-id="19f0d-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="19f0d-107">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="19f0d-107">Recommended action</span></span>

<span data-ttu-id="19f0d-108">Rufen Sie anstelle der Überladung <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> auf, die zwei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="19f0d-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="19f0d-109">Wenn Sie Bootstrap 3 verwenden, fügen Sie außerdem die folgende Zeile in einem `<PropertyGroup>`-Element in Ihrer Projektdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="19f0d-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="19f0d-110">Kategorie</span><span class="sxs-lookup"><span data-stu-id="19f0d-110">Category</span></span>

<span data-ttu-id="19f0d-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="19f0d-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19f0d-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="19f0d-112">Affected APIs</span></span>

[<span data-ttu-id="19f0d-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="19f0d-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
