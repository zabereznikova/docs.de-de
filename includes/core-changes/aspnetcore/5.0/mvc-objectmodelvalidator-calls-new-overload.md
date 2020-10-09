---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609296"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a>MVC: ObjectModelValidator ruft eine neue Überladung von ValidationVisitor.Validate auf

In ASP.NET Core 5.0 wurde eine Überladung von <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> hinzugefügt. Die neue Überladung akzeptiert die oberste Modellinstanz, die Eigenschaften enthält:

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> ruft diese neue Überladung von `ValidationVisitor` für die Validierung auf. Diese neue Überladung ist relevant, wenn Ihre Validierungsbibliothek mit dem ASP.NET Core MVC-Modellvalidierungssystem integriert ist.

Weitere Informationen finden Sie im GitHub-Issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="old-behavior"></a>Altes Verhalten

`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a>Neues Verhalten

`ObjectModelValidator` ruft während der Modellvalidierung die folgende Überladung auf:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde eingeführt, um Validierungssteuerelemente wie <xref:System.ComponentModel.DataAnnotations.CompareAttribute> zu unterstützen, die von der Überprüfung anderer Eigenschaften abhängig sind.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Validierungsframeworks, die von `ObjectModelValidator` abhängig sind, um die vorhandene Überladung von `ValidationVisitor` aufzurufen, müssen die neue Methode überschreiben, wenn .NET 5.0 oder höher als Zielversion verwendet wird:

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
