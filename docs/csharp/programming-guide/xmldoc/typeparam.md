---
title: <typeparam> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <typeparam> ein. Dieses Tag wird im Kommentar für eine generische Typ- oder Methodendeklaration verwendet, um einen Typparameter zu beschreiben.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380786"
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
