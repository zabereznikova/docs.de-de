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
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875532"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)

Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.  
  
## <a name="remarks"></a>Bemerkungen  

 Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft. Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern ( `< >` ) direkt an die Deklarations Anweisung anfügen.  
  
 Wenn sich ein Attribut nicht nur auf das folgende Element bezieht, sondern auf die gesamte Assembly, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem- `Assembly` Schlüsselwort. Wenn dies für das aktuelle Assemblymodul gilt, verwenden Sie das [Module](module-keyword.md) -Schlüsselwort.  
  
 Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo. vb anwenden. in diesem Fall müssen Sie keinen Attribut Block in der Haupt Quell Code Datei verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Mond \<keyword>](module-keyword.md)
- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
