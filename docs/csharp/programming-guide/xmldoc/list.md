---
title: <list> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <list> ein. Dieses Tag wird verwendet, um Tabellen und die zugehörige Definition sowie Aufzählungen oder nummerierte Listen mithilfe von item-Blöcken zu erstellen.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 361c2e6f343554a9b8519c3b2e41219b209e682d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381865"
---
# <a name="list-c-programming-guide"></a>\<list> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a>Parameter

- `term`

  Ein zu definierender Begriff, der in `description` definiert wird.

- `description`

  Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.
  
## <a name="remarks"></a>Hinweise

Der `<listheader>`-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren. Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.

Jedes Element der Liste wird mit einem `<item>`-Block angegeben. Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben. Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.

Eine Liste oder Tabelle kann so viele `<item>`-Blöcke besitzen wie nötig.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
