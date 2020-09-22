---
title: Mond <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 6c4f24ad161302835be683e9d324ce32b16c4087
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867984"
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
