---
title: 'Breaking Change: MVC: ObjectModelValidator ruft eine neue Überladung von ValidationVisitor.Validate auf'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „MVC: ObjectModelValidator ruft eine neue Überladung von ValidationVisitor.Validate auf'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b28c357f51291a4f73889d5d413a983f79e09daf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759546"
---
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="9dbd8-103">MVC: ObjectModelValidator ruft eine neue Überladung von ValidationVisitor.Validate auf</span><span class="sxs-lookup"><span data-stu-id="9dbd8-103">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="9dbd8-104">In ASP.NET Core 5.0 wurde eine Überladung von <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9dbd8-104">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="9dbd8-105">Die neue Überladung akzeptiert die oberste Modellinstanz, die Eigenschaften enthält:</span><span class="sxs-lookup"><span data-stu-id="9dbd8-105">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="9dbd8-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> ruft diese neue Überladung von `ValidationVisitor` für die Validierung auf.</span><span class="sxs-lookup"><span data-stu-id="9dbd8-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="9dbd8-107">Diese neue Überladung ist relevant, wenn Ihre Validierungsbibliothek mit dem ASP.NET Core MVC-Modellvalidierungssystem integriert ist.</span><span class="sxs-lookup"><span data-stu-id="9dbd8-107">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="9dbd8-108">Weitere Informationen finden Sie im GitHub-Issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="9dbd8-108">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9dbd8-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9dbd8-109">Version introduced</span></span>

<span data-ttu-id="9dbd8-110">5.0</span><span class="sxs-lookup"><span data-stu-id="9dbd8-110">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="9dbd8-111">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="9dbd8-111">Old behavior</span></span>

<span data-ttu-id="9dbd8-112">`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:</span><span class="sxs-lookup"><span data-stu-id="9dbd8-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a><span data-ttu-id="9dbd8-113">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="9dbd8-113">New behavior</span></span>

<span data-ttu-id="9dbd8-114">`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:</span><span class="sxs-lookup"><span data-stu-id="9dbd8-114">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a><span data-ttu-id="9dbd8-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="9dbd8-115">Reason for change</span></span>

<span data-ttu-id="9dbd8-116">Diese Änderung wurde eingeführt, um Validierungssteuerelemente wie <xref:System.ComponentModel.DataAnnotations.CompareAttribute> zu unterstützen, die von der Überprüfung anderer Eigenschaften abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="9dbd8-116">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9dbd8-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="9dbd8-117">Recommended action</span></span>

<span data-ttu-id="9dbd8-118">Validierungsframeworks, die von `ObjectModelValidator` abhängig sind, um die vorhandene Überladung von `ValidationVisitor` aufzurufen, müssen die neue Methode überschreiben, wenn .NET 5.0 oder höher als Zielversion verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="9dbd8-118">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a><span data-ttu-id="9dbd8-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9dbd8-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
