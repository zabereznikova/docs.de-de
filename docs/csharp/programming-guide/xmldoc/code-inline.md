---
title: <c> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793456"
---
# <a name="c-c-programming-guide"></a>\<c> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<c>text</c>
```

## <a name="parameters"></a>Parameter

- `text`

  Der Text, der als Code angegeben werden soll.

## <a name="remarks"></a>Hinweise

Mit dem \<c>-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll. Zum Angeben mehrerer Zeilen als Code wird [\<code>](./code.md) verwendet.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
