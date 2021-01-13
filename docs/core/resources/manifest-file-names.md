---
title: Generieren von Manifestdateinamen mit MSBuild
description: Beschreibt die Faktoren bei der Benennung von Manifestdateien von Ressourcen beim Kompilieren mit MSBuild
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866381"
---
# <a name="how-resource-manifest-files-are-named"></a>Benennen von Manifestdateien von Ressourcen

Wenn MSBuild ein .NET Core-Projekt kompiliert, werden XML-Ressourcendateien mit der Dateierweiterung *.resx* in *.resources*-Binärdateien konvertiert. Die Binärdateien werden in die Ausgabe des Compilers eingebettet und können vom <xref:System.Resources.ResourceManager> gelesen werden. In diesem Artikel wird beschrieben, wie MSBuild die Namen für die jeweiligen *.resources*-Dateien auswählt.

> [!TIP]
> Wenn Sie der Projektdatei explizit ein Ressourcenelement hinzufügen und dieses auch [in den standardmäßigen Include-Globs für .NET Core](../project-sdk/overview.md#default-compilation-includes) enthalten ist, erhalten Sie einen Buildfehler. Um Ressourcendateien manuell als `EmbeddedResource`-Elemente einzubeziehen, legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf „false“ fest.

## <a name="default-name"></a>Standardname

In .NET Core 3.0 und höher wird für ein Ressourcenmanifest der Standardname verwendet, wenn die beiden folgenden Bedingungen erfüllt sind:

- Die Ressourcendatei ist nicht explizit in der Projektdatei als `EmbeddedResource`-Element mit den Metadaten `LogicalName`, `ManifestResourceName` oder `DependentUpon` enthalten.
- Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft ist in der Projektdatei nicht auf `false` festgelegt. Standardmäßig ist diese Eigenschaft auf `true`festgelegt. Weitere Informationen finden Sie unter [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).

Wenn die Ressourcendatei mit einer Quelldatei ( *.cs* oder *.vb*) desselben Stammdateinamens zusammengestellt wird, wird der vollständige Name des ersten Typs, der in der Quelldatei definiert ist, als Manifestdateiname verwendet. Wenn beispielsweise `MyNamespace.Form1` der erste Typ ist, der in der *Form1.cs*-Datei definiert ist, und *Form1.cs* mit *Form1.resx* angeordnet ist, lautet der generierte Manifestname für diese Ressourcendatei *MyNamespace.Form1.resources*.

## <a name="logicalname-metadata"></a>LogicalName-Metadaten

Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `LogicalName`-Metadaten enthalten ist, wird der `LogicalName`-Wert als Manifestname verwendet. `LogicalName` hat Vorrang vor anderen Metadaten oder Einstellungen.

Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

Oder

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a>ManifestResourceName-Metadaten

Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `ManifestResourceName`-Metadaten enthalten ist (und `LogicalName` fehlt), wird als Manifestdateiname der `ManifestResourceName`-Wert in Kombination mit der Dateierweiterung *.resources* verwendet.

Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *SomeName.resources*.

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a>DependentUpon-Metadaten

Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `DependentUpon`-Metadaten enthalten ist (und sowohl `LogicalName` als auch `ManifestResourceName` fehlen), werden Informationen aus der Quelldatei, die von `DependentUpon` definiert werden, für den Dateinamen des Ressourcenmanifests verwendet. Genauer gesagt wird der Name des ersten Typs, der in der Quelldatei definiert ist, wie folgt im Manifestnamen verwendet: *Namespace.Classname\[.Culture].resources*.

Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *Namespace.Classname.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a>EmbeddedResourceUseDependentUponConvention-Eigenschaft

Wenn `EmbeddedResourceUseDependentUponConvention` auf `false` in der Projektdatei festgelegt ist, basieren die Manifestdateinamen der jeweiligen Ressourcen auf dem Stammnamespace für das Projekt und auf dem relativen Pfad vom Projektstamm zur *.resx*-Datei. Genauer gesagt lautet der Name der generierten Manifestdatei der Ressource *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. Diese Logik wird auch verwendet, um Manifestnamen in .NET Core-Versionen vor 3.0 zu generieren.

> [!NOTE]
>
> - Wenn `RootNamespace` nicht definiert ist, wird standardmäßig der Projektname verwendet.
> - Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element in der Projektdatei angegeben werden, gilt diese Benennungsregel nicht für diese Ressourcendatei.

## <a name="see-also"></a>Siehe auch

- [Funktionsweise der Benennung von Manifestressourcen](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [MSBuild-Eigenschaften für .NET Core SDK-Projekte](../project-sdk/msbuild-props.md)
- [Breaking Changes in MSBuild](../compatibility/msbuild.md)
