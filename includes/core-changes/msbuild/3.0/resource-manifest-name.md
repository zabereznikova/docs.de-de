---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206213"
---
### <a name="resource-manifest-file-name-change"></a>Änderung des Manifestdateinamens der Ressource

Ab .NET Core 3.0 generiert MSBuild im Standardfall einen anderen Manifestdateinamen für Ressourcendateien.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="change-description"></a>Änderungsbeschreibung

Vor .NET Core 3.0 hat MSBuild im Muster `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` einen Manifestdateinamen generiert, wenn für ein `EmbeddedResource`-Element in der Projektdatei nicht `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten angegeben wurden. Wenn `RootNamespace` nicht in der Projektdatei definiert ist, wird standardmäßig der Projektname verwendet. Beispielsweise lautete der Name des generierten Manifests für eine Ressourcendatei mit dem Namen *Form1.resx* im Stammverzeichnis des Projekts *MyProject.Form1.resources*.

Ab .NET Core 3.0 verwendet MSBuild Typinformationen aus der Quelldatei, wenn eine Ressourcendatei mit einer Quelldatei desselben Namens (z. B. *Form1.resx* und *Form1.cs*) angeordnet wird, um den Manifestdateinamen im Muster `<Namespace>.<ClassName>.resources` zu generieren. Der Namespace- und Klassenname werden aus dem ersten Typ in der angeordneten Quelldatei extrahiert. Beispielsweise lautet der generierte Manifestname für eine Ressourcendatei mit dem Namen *Form1.resx*, die mit einer Quelldatei mit dem Namen *Form1.cs* angeordnet wird, *MyNamespace.Form1.resources*. Wichtig ist zu beachten, dass der erste Teil des Dateinamens sich von früheren Versionen von .NET Core unterscheidet (*MyNamespace* anstelle von *MyProject*).

> [!NOTE]
> Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element in der Projektdatei angegeben sind, wirkt sich diese Änderung nicht auf diese Ressourcendatei aus.

Dieser Breaking Change wurde mit dem Hinzufügen der `EmbeddedResourceUseDependentUponConvention`-Eigenschaft zu .NET Core-Projekten eingeführt. Standardmäßig werden Ressourcendateien nicht explizit in einer .NET Core-Projektdatei aufgelistet, sodass Ihnen keine `DependentUpon`-Metadaten zur Verfügung stehen, um anzugeben, wie die generierte *RESOURCES*-Datei benannt werden soll. Wenn `EmbeddedResourceUseDependentUponConvention` dem Standard entsprechend auf `true` festgelegt ist, sucht MSBuild nach einer angeordneten Quelldatei und extrahiert einen Namespace- und Klassennamen aus dieser Datei. Wenn Sie `EmbeddedResourceUseDependentUponConvention` auf `false` festlegen, generiert MSBuild den Namen des Manifests gemäß dem vorherigen Verhalten, wobei `RootNamespace` und der relative Dateipfad kombiniert werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

In den meisten Fällen ist keine Aktion seitens des Entwicklers erforderlich, und Ihre App sollte weiterhin funktionieren. Wenn diese Änderung jedoch Ihre App beeinträchtigt, haben Sie folgende Möglichkeiten:

- Ändern Sie den Code so, dass er den neuen Manifestnamen erwartet.

- Um die neue Namenskonvention zu umgehen, legen Sie in Ihrer Projektdatei `EmbeddedResourceUseDependentUponConvention` auf `false` fest.

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a>Kategorie

MSBuild

#### <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend
