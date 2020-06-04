---
title: Mond<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362423"
---
# <a name="module-keyword-visual-basic"></a>Module \<keyword> (Visual Basic)
Gibt an, dass ein Attribut am Anfang einer Quelldatei für das aktuelle Assemblymodul gilt.  
  
## <a name="remarks"></a>Bemerkungen  
 Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft. Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern ( `< >` ) direkt an die Deklarations Anweisung anfügen.  
  
 Wenn ein Attribut nicht nur dem folgenden Element, sondern dem aktuellen Assemblymodul entspricht, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem- `Module` Schlüsselwort. Wenn Sie für die gesamte Assembly gilt, verwenden Sie das [Assembly](assembly.md) -Schlüsselwort.  
  
 Der- `Module` Modifizierer ist nicht mit der [Modul Anweisung](../statements/module-statement.md)identisch.  
  
## <a name="see-also"></a>Weitere Informationen

- [Assembly](assembly.md)
- [Module-Anweisung](../statements/module-statement.md)
- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
