---
title: <see> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <see>. Mit diesem Tag können Sie einen Link im Text angeben, z. B. durch Verwendung eines cref-Attributs.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381930"
---
# <a name="see-c-programming-guide"></a>\<see> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parameter

- cref = "`member`"

  Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. Setzen Sie *member* in doppelte Anführungszeichen (" ").

## <a name="remarks"></a>Hinweise

Mit dem `<see>`-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](./seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll. Verwenden Sie das [cref-Attribut](./cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen. Außerdem ist ``href`` ein gültiges Attribut, das als Hyperlink fungiert.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

Im folgenden Beispiel wird ein `<see>`-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
