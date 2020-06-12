---
title: <param> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 396ed716c246091a674268020261069f36dd2be8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287323"
---
# <a name="param-c-programming-guide"></a>\<param> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>Parameter

- `name`

  Der Name eines Methodenparameters. Setzen Sie den Namen in doppelte Anführungszeichen (" ").

- `description`

  Eine Beschreibung für den Parameter

## <a name="remarks"></a>Hinweise

Das `<param>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben. Verwenden Sie mehrere `<param>`-Tags, um mehrere Parameter zu dokumentieren.

Der Text für das `<param>`-Tag wird in IntelliSense, dem Objektkatalog und im Webbericht über Codekommentare angezeigt.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
