---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394363"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="8e4e6-101">Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="8e4e6-102">In ASP.NET Core 3.0 wurde eine Funktion für statische Webressourcen eingeführt, an die die Identitäts-Benutzeroberfläche nun angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8e4e6-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8e4e6-103">Change description</span></span>

<span data-ttu-id="8e4e6-104">Die Identitäts-Benutzeroberfläche wurde an die Funktion für statische Webressourcen angepasst:</span><span class="sxs-lookup"><span data-stu-id="8e4e6-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="8e4e6-105">Die Auswahl des Frameworks erfolgt mithilfe der `IdentityUIFrameworkVersion`-Eigenschaft in Ihrer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="8e4e6-106">Bootstrap 4 ist das Standardframework für die Identitäts-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="8e4e6-107">Bootstrap 3 hat das Ende des Lebenszyklus erreicht, und Sie sollten zu einer unterstützten Version migrieren.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8e4e6-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8e4e6-108">Version introduced</span></span>

<span data-ttu-id="8e4e6-109">3.0</span><span class="sxs-lookup"><span data-stu-id="8e4e6-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8e4e6-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="8e4e6-110">Old behavior</span></span>

<span data-ttu-id="8e4e6-111">Das Standardframework für die Identitäts-Benutzeroberfläche war bisher **Bootstrap 3**.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="8e4e6-112">Das Benutzeroberflächen-Framework kann mithilfe eines Parameters im `AddIdentityUI`-Methodenaufruf in `Startup.ConfigureServices` konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-112">The UI framework could be configured using a parameter to the `AddIdentityUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8e4e6-113">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="8e4e6-113">New behavior</span></span>

<span data-ttu-id="8e4e6-114">Das Standardframework für die Identitäts-Benutzeroberfläche ist nun **Bootstrap 4**.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="8e4e6-115">Das Benutzeroberflächen-Framework muss in der Projektdatei und nicht mehr im `AddIdentityUI`-Methodenaufruf konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-115">The UI framework must be configured in your project file, instead of in the `AddIdentityUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8e4e6-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="8e4e6-116">Reason for change</span></span>

<span data-ttu-id="8e4e6-117">Durch die Einführung der Funktion für statische Webressourcen musste die Konfiguration des Benutzeroberflächen-Frameworks auf MSBuild umgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="8e4e6-118">Die Entscheidung über das einzubettende Framework wird zur Buildzeit und nicht zur Laufzeit getroffen.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8e4e6-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8e4e6-119">Recommended action</span></span>

<span data-ttu-id="8e4e6-120">Überprüfen Sie die Website-Benutzeroberfläche, um sicherzustellen, dass die neuen Bootstrap 4-Komponenten kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="8e4e6-121">Verwenden Sie ggf. die MSBuild-Eigenschaft `IdentityUIFrameworkVersion`, um zu Bootstrap 3 zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="8e4e6-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="8e4e6-122">Fügen Sie die-Eigenschaft einem `<PropertyGroup>`-Element in Ihrer Projektdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="8e4e6-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="8e4e6-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8e4e6-123">Category</span></span>

<span data-ttu-id="8e4e6-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8e4e6-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8e4e6-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8e4e6-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
