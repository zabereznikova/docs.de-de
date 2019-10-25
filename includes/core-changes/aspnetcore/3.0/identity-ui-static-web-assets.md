---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394363"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>Identität: Benutzeroberfläche verwendet Funktion für statische Webressourcen.

In ASP.NET Core 3.0 wurde eine Funktion für statische Webressourcen eingeführt, an die die Identitäts-Benutzeroberfläche nun angepasst wurde.

#### <a name="change-description"></a>Änderungsbeschreibung

Die Identitäts-Benutzeroberfläche wurde an die Funktion für statische Webressourcen angepasst:

- Die Auswahl des Frameworks erfolgt mithilfe der `IdentityUIFrameworkVersion`-Eigenschaft in Ihrer Projektdatei.
- Bootstrap 4 ist das Standardframework für die Identitäts-Benutzeroberfläche. Bootstrap 3 hat das Ende des Lebenszyklus erreicht, und Sie sollten zu einer unterstützten Version migrieren.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Standardframework für die Identitäts-Benutzeroberfläche war bisher **Bootstrap 3**. Das Benutzeroberflächen-Framework kann mithilfe eines Parameters im `AddIdentityUI`-Methodenaufruf in `Startup.ConfigureServices` konfiguriert werden.

#### <a name="new-behavior"></a>Neues Verhalten

Das Standardframework für die Identitäts-Benutzeroberfläche ist nun **Bootstrap 4**. Das Benutzeroberflächen-Framework muss in der Projektdatei und nicht mehr im `AddIdentityUI`-Methodenaufruf konfiguriert werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Durch die Einführung der Funktion für statische Webressourcen musste die Konfiguration des Benutzeroberflächen-Frameworks auf MSBuild umgestellt werden. Die Entscheidung über das einzubettende Framework wird zur Buildzeit und nicht zur Laufzeit getroffen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Überprüfen Sie die Website-Benutzeroberfläche, um sicherzustellen, dass die neuen Bootstrap 4-Komponenten kompatibel sind. Verwenden Sie ggf. die MSBuild-Eigenschaft `IdentityUIFrameworkVersion`, um zu Bootstrap 3 zurückzukehren. Fügen Sie die-Eigenschaft einem `<PropertyGroup>`-Element in Ihrer Projektdatei hinzu:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
