---
title: Assembly
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351649"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.  
  
## <a name="remarks"></a>Hinweise  
 Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft. Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern (`< >`) direkt an die Deklarations Anweisung anfügen.  
  
 Wenn sich ein Attribut nicht nur auf das folgende Element bezieht, sondern auf die gesamte Assembly, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem `Assembly`-Schlüsselwort. Wenn dies für das aktuelle Assemblymodul gilt, verwenden Sie das [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) -Schlüsselwort.  
  
 Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo. vb anwenden. in diesem Fall müssen Sie keinen Attribut Block in der Haupt Quell Code Datei verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
