---
title: <returns> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <returns> ein. Dieses Tag wird im Kommentar für eine Methodendeklaration verwendet, um den Rückgabewert zu beschreiben.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381397"
---
# <a name="returns-c-programming-guide"></a>\<returns> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<returns>description</returns>
```

## <a name="parameters"></a>Parameter

- `description`

  Eine Beschreibung des Rückgabewerts.

## <a name="remarks"></a>Hinweise

Das `<returns>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um den Rückgabewert zu beschreiben.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
