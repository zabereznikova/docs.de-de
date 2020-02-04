---
title: <exception> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 14318ac0b0cdf781d0488eecaf934879017d91f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789800"
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

Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können. Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../exceptions/index.md).

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](recommended-tags-for-documentation-comments.md)
