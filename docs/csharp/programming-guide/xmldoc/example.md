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
ms.openlocfilehash: e8d26f82562cc5140662f5b32ea9fedf5481d8f8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287385"
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

Mit dem `<example>`-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden. Dies schließt im Allgemeinen die Verwendung des [\<code>](./code.md)-Tags ein.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
