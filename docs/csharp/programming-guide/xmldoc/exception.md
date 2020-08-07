---
title: <exception> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <exception>. Mit diesem Tag können Sie angeben, welche Ausnahmen ausgelöst werden können. Es kann auf Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381735"
---
# <a name="exception-c-programming-guide"></a>\<exception> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>Parameter

- cref = " `member`"

  Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist. Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.

  Weitere Informationen zum Formatieren von `member` für das Verweisen auf einen generischen Typ finden Sie unter [Verarbeiten der XML-Datei](processing-the-xml-file.md).

- `description`

  Eine Beschreibung der Ausnahme.

## <a name="remarks"></a>Hinweise

Mit dem Tag `<exception>` können Sie angeben, welche Ausnahmen ausgelöst werden können. Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../exceptions/index.md).

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](recommended-tags-for-documentation-comments.md)
