---
title: <example> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <example> ein. Mit diesem Tag können Sie ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliotheksmembers angeben.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381527"
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

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
