---
title: <include> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <include> ein. Mit diesem Tag können Sie auf Kommentare in einer anderen Datei verweisen, die die Typen und Member in Ihrem Quellcode beschreiben.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 15a99444d464594cc91a7c8805c564c703c3b608
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381904"
---
# <a name="include-c-programming-guide"></a>\<include> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a>Parameter

- `filename`

  Der Name der XML-Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad relativ zur Quellcodedatei qualifiziert werden. `filename` muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.

- `tagpath`

  Der Pfad der Tags in `filename`, der zum Tag `name` führt. Der Pfad muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.

- `name`

  Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` besitzt eine `id`.

- `id`

Die ID für das Tag, das sich vor den Kommentaren befindet. Die ID muss in doppelte Anführungszeichen („“) eingeschlossen werden.

## <a name="remarks"></a>Hinweise

Mit dem `<include>`-Tag können Sie auf Kommentare in einer anderen Datei verweisen, in denen die Typen und Member in Ihrem Quellcode beschrieben werden. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei. Durch das Ablegen der Dokumentation in einer separaten Datei können Sie die Quellcodeverwaltung unabhängig vom Quellcode auf die Dokumentation anwenden. Eine Person kann die Quellcodedatei auschecken, eine andere die Dokumentationsdatei.

Das `<include>`-Tag verwendet die XPath-Syntax. Weitere Anpassungsmöglichkeiten bei der Verwendung von `<include>` finden Sie in der XPath-Dokumentation.

## <a name="example"></a>Beispiel

Dies ist ein Beispiel einer Mehrfachdatei. Die folgende Datei ist die erste, die `<include>` verwendet.

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

Die zweite Datei, *xml_include_tag.doc*, enthält die folgenden Dokumentationskommentare.

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Programmausgabe

Die folgende Ausgabe wird generiert, wenn Sie die Klassen „Test“ und „Test2“ mit der folgenden Befehlszeile kompilieren: `-doc:DocFileName.xml.` In Visual Studio geben Sie die Option für XML-Dokumentkommentare im Buildbereich des Projekt-Designers an. Erkennt der C#-Compiler das `<include>`-Tag, so sucht er statt in der aktuellen Quelldatei in *xml_include_tag.doc* nach Dokumentationskommentaren. Der Compiler generiert dann *DocFileName.xml*. Dies ist die Datei, die von Dokumentationstools wie z. B. [Sandcastle](https://github.com/EWSoftware/SHFB) genutzt wird, um die endgültige Dokumentation zu erzeugen.  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
