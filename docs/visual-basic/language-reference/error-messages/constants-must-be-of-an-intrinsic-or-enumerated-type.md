---
title: "Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp.
Sie haben versucht, eine Konstante als eine Klasse, Struktur oder Arraytyp oder als eine von einem enthaltenden generischen Typ definierten Typparameter deklariert.  
  
 Konstanten müssen einen systeminternen Typ sein (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, oder `UShort`), oder ein `Enum` -Typ basierend auf ganzzahligen Typen.  
  
 **Fehler-ID:** BC30424  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie die Konstante als systeminterne Funktion oder `Enum` Typ.  
  
2.  Eine Konstante kann auch ein spezieller Wert wie z. B. `True`, `False`, oder `Nothing`. Der Compiler betrachtet diese vordefinierten Werte den entsprechenden systeminternen Typ aufweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Datentypen](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)
