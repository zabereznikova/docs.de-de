---
title: <remarks> – C#-Programmierhandbuch
description: 'Erfahren Sie mehr über das XML-Tag <remarks> ein. Dieses Tag wird verwendet, um Informationen zu einem Typ hinzuzufügen und die hiermit angegebenen Informationen zu ergänzen: <summary>.'
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381501"
---
# <a name="remarks-c-programming-guide"></a>\<remarks> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parameter

- `Description`

  Eine Beschreibung des Members

## <a name="remarks"></a>Hinweise

Das Tag `<remarks>` wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](./summary.md) angegebenen Informationen ergänzt. Diese Informationen werden im Fenster des Objektkatalogs angezeigt.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
