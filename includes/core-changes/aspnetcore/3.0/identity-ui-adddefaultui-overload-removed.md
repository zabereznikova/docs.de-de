---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522661"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="ca440-101">Identität: AddDefaultUI-Methodenüberladung wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="ca440-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="ca440-102">Ab ASP.NET Core 3.0 ist die <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>-Methodenüberladung nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ca440-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ca440-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ca440-103">Version introduced</span></span>

<span data-ttu-id="ca440-104">3.0</span><span class="sxs-lookup"><span data-stu-id="ca440-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ca440-105">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ca440-105">Reason for change</span></span>

<span data-ttu-id="ca440-106">Diese Änderung wurde aufgrund der Einführung der Funktion für statische Webressourcen notwendig.</span><span class="sxs-lookup"><span data-stu-id="ca440-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ca440-107">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ca440-107">Recommended action</span></span>

<span data-ttu-id="ca440-108">Rufen Sie anstelle der Überladung <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="ca440-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="ca440-109">Wenn Sie Bootstrap 3 verwenden, fügen Sie außerdem die folgende Zeile in einem `<PropertyGroup>`-Element in Ihrer Projektdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="ca440-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="ca440-110">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ca440-110">Category</span></span>

<span data-ttu-id="ca440-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca440-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ca440-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ca440-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
