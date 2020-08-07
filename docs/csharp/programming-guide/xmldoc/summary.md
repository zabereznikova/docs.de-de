---
title: <summary> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <summary> , das zur Beschreibung eines Typs oder Typmembers verwendet wird. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f9243e598aaf0c12dd48b48045f461b4b307c18f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380604"
---
# <a name="summary-c-programming-guide"></a>\<summary> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<summary>description</summary>
```

## <a name="parameters"></a>Parameter

- `description`

  Eine Übersicht des Objekts.

## <a name="remarks"></a>Hinweise

Das `<summary>`-Tag sollte für die Beschreibung eines Typs oder Typmembers verwendet werden. Verwenden Sie [\<remarks>](./remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen. Verwenden Sie das [cref-Attribut](./cref-attribute.md), um Dokumentationswerkzeuge wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) zum Erstellen von internen Links zu Dokumentationsseiten für Codeelemente zu aktivieren.

Der Text für das `<summary>`-Tag stellt die einzige Informationsquelle in Bezug auf den Typ in IntelliSense dar und wird auch im Fenster „Objektkatalog“ angezeigt.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten. Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

Das vorherige Beispiel erzeugt folgende XML-Datei.

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a>Beispiel

Das folgende Beispiel stellt dar, wie Sie einen `cref`-Verweis auf generische Typen erstellen.

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

Das vorherige Beispiel erzeugt folgende XML-Datei.

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
