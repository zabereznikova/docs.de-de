---
title: <paramref> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <paramref>. Mit diesem Tag können Sie angeben, dass ein Wort im Code ein Parameter ist.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381839"
---
# <a name="paramref-c-programming-guide"></a>\<paramref> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>Parameter

- `name`

  Der Name des Parameters, auf den verwiesen wird. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").

## <a name="remarks"></a>Hinweise

Das Tag `<paramref>` bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z. B. in einem `<summary>`- oder `<remarks>`-Block, auf einen Parameter bezieht. Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
