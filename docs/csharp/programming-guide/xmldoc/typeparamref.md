---
title: <typeparamref> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789658"
---
# <a name="typeparamref-c-programming-guide"></a>\<typeparamref> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a>Parameter

- `name`

  Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").

## <a name="remarks"></a>Hinweise

Weitere Informationen zu den Typparametern in generischen Typen und Methoden, finden Sie unter [Generics](../generics/index.md).

Verwenden Sie dieses Tag, um Consumern der Dokumentationsdatei zu ermöglichen, das Wort auf unterschiedliche Weise zu formatieren, z.B. in Kursivschrift.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
