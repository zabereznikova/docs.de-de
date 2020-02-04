---
title: <example> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: 615eccbc427b6a5bbbed061acd0c8b0b9be7f46c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789816"
---
# <a name="example-c-programming-guide"></a>\<example> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<example>description</example>
```

## <a name="parameters"></a>Parameter

- `description`

  Eine Beschreibung des Codebeispiels.

## <a name="remarks"></a>Hinweise

Mit dem \<example>-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden. Dies schließt im Allgemeinen die Verwendung des [\<code](./code.md)-Tags ein.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
