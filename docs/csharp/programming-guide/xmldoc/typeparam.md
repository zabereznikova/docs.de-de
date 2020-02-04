---
title: <typeparam> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793363"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>Parameter

- `name`

  Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").

- `description`

  Eine Beschreibung für den Typparameter.

## <a name="remarks"></a>Hinweise

Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben. Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.

Weitere Informationen finden Sie unter [Generics](../generics/index.md).

Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
