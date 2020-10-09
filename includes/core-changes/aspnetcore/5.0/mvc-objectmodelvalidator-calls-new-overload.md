---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609296"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="59085-101">MVC: ObjectModelValidator ruft eine neue Überladung von ValidationVisitor.Validate auf</span><span class="sxs-lookup"><span data-stu-id="59085-101">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="59085-102">In ASP.NET Core 5.0 wurde eine Überladung von <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="59085-102">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="59085-103">Die neue Überladung akzeptiert die oberste Modellinstanz, die Eigenschaften enthält:</span><span class="sxs-lookup"><span data-stu-id="59085-103">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="59085-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> ruft diese neue Überladung von `ValidationVisitor` für die Validierung auf.</span><span class="sxs-lookup"><span data-stu-id="59085-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="59085-105">Diese neue Überladung ist relevant, wenn Ihre Validierungsbibliothek mit dem ASP.NET Core MVC-Modellvalidierungssystem integriert ist.</span><span class="sxs-lookup"><span data-stu-id="59085-105">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="59085-106">Weitere Informationen finden Sie im GitHub-Issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="59085-106">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="59085-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="59085-107">Version introduced</span></span>

<span data-ttu-id="59085-108">5.0</span><span class="sxs-lookup"><span data-stu-id="59085-108">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="59085-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="59085-109">Old behavior</span></span>

<span data-ttu-id="59085-110">`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:</span><span class="sxs-lookup"><span data-stu-id="59085-110">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a><span data-ttu-id="59085-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="59085-111">New behavior</span></span>

<span data-ttu-id="59085-112">`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:</span><span class="sxs-lookup"><span data-stu-id="59085-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a><span data-ttu-id="59085-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="59085-113">Reason for change</span></span>

<span data-ttu-id="59085-114">Diese Änderung wurde eingeführt, um Validierungssteuerelemente wie <xref:System.ComponentModel.DataAnnotations.CompareAttribute> zu unterstützen, die von der Überprüfung anderer Eigenschaften abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="59085-114">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="59085-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="59085-115">Recommended action</span></span>

<span data-ttu-id="59085-116">Validierungsframeworks, die von `ObjectModelValidator` abhängig sind, um die vorhandene Überladung von `ValidationVisitor` aufzurufen, müssen die neue Methode überschreiben, wenn .NET 5.0 oder höher als Zielversion verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="59085-116">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a><span data-ttu-id="59085-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="59085-117">Category</span></span>

<span data-ttu-id="59085-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="59085-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="59085-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="59085-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
