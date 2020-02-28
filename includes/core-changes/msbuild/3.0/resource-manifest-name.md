---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451886"
---
### <a name="resource-manifest-file-names"></a>Manifestdateinamen von Ressourcen

Ab .Net Core 3.0 hat sich der generierte Manifestdateiname von Ressourcen geändert.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="change-description"></a>Änderungsbeschreibung

Wenn vor . NET Core 3.0 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile)-Metadaten für eine Ressourcendatei ( *.resx*) in der MSBuild-Projektdatei festgelegt wurden, lautete der generierte Manifestname *Namespace.Classname.resources*. Wenn [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) nicht festgelegt wurde, lautete der generierte Manifestname *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.

Ab .NET Core 3.0 wird, wenn eine *RESX*-Datei mit einer gleichnamigen Quelldatei zusammengestellt wird, z. B. in Windows Forms-Anwendungen, der Manifestname der Ressource aus dem vollständigen Namen des ersten Typs in der Quelldatei generiert. Wenn beispielsweise *Type.cs* mit *Type.resx* zusammengestellt wird, lautet der generierte Manifestname *Namespace.Classname.resources*. Wenn Sie jedoch eines der Attribute der `EmbeddedResource`-Eigenschaft in der *RESX*-Datei ändern, kann der generierte Manifestdateiname anders lauten:

- Wenn das `LogicalName`-Attribut der `EmbeddedResource`-Eigenschaft festgelegt ist, wird dieser Wert als Manifestdateiname der Ressource verwendet.

  Beispiele:

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **Generierter Manifestdateiname der Ressource**: *SomeName.resources* (unabhängig vom *RESX*-Dateinamen oder der Kultur oder anderen Metadaten).

- Falls `LogicalName` nicht festgelegt ist, aber das `ManifestResourceName`-Attribut der `EmbeddedResource`-Eigenschaft festgelegt ist, wird sein Wert in Kombination mit der Dateierweiterung *.resources* als Manifestdateiname der Ressource verwendet.

  Beispiele:

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **Generierter Manifestdateiname der Ressource**: *SomeName.resources* oder *SomeName.fr-FR.resources*.

- Wenn die vorherigen Regeln nicht zutreffen und das `DependentUpon`-Attribut des `EmbeddedResource`-Elements auf eine Quelldatei festgelegt ist, wird der Typname der ersten Klasse in der Quelldatei im Manifestdateinamen der Ressource verwendet. Genauer gesagt lautet der generierte Dateiname *Namespace.Classname\[.Culture].resources*.

  Beispiele:

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **Generierter Manifestdateiname der Ressource**: *Namespace.Classname.resources* oder *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` der Name der ersten Klasse in *MyTypes.cs* ist).

- Wenn die vorherigen Regeln nicht zutreffen, ist `EmbeddedResourceUseDependentUponConvention` gleich `true` (Standard für .NET Core), und es eine mit einer *RESX*-Datei zusammengestellte Quelldatei gibt, die den gleichen Basisdateinamen hat, wird die *RESX*-Datei von der übereinstimmenden Quelldatei abhängig gemacht. Der generierte Name ist der gleiche wie in der vorherigen Regel. Dies ist die Standardeinstellungsregel für .NET Core-Projekte.
  
  Beispiele:
  
  Die Dateien *MyTypes.cs* und *MyTypes.resx* oder *MyTypes.fr-FR.resx* befinden sich im gleichen Ordner.
  
  **Generierter Manifestdateiname der Ressource**: *Namespace.Classname.resources* oder *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` der Name der ersten Klasse in *MyTypes.cs* ist).
    
- Wenn keine der vorherigen Regeln zutrifft, lautet der Name der generierten Manifestdatei der Ressource *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. Der relative Pfad ist der Wert des `Link`-Attributs des `EmbeddedResource`-Elements, falls festgelegt. Andernfalls ist der relative Pfad der Wert des `Identity`-Attributs des `EmbeddedResource`-Elements. In Visual Studio ist dies der Pfad vom Projektstamm zur Datei im Projektmappen-Explorer.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie mit den generierten Manifestnamen unzufrieden sind, haben Sie folgende Möglichkeiten:

- Ändern Sie die Metadaten Ihrer Ressourcendatei gemäß einer der zuvor beschriebenen Benennungsregeln.

- Legen Sie in Ihrer Projektdatei `EmbeddedResourceUseDependentUponConvention` auf `false` fest, um die neue Konvention vollständig abzulehnen:

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > Wenn die Attribute `LogicalName` oder `ManifestResourceName` vorhanden sind, werden ihre Werte weiterhin für den generierten Dateinamen verwendet.

#### <a name="category"></a>Kategorie

MSBuild

#### <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend
