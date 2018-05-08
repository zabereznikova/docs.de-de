---
title: Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
Eine Prozedur ist mit einem optionalen Parameter deklariert, der einen Typparameter, der nicht eingeschränkt wird verwendet, um ein Verweistyp sein muss.  
  
 Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben. Wenn der Parameter ein Verweistyp ist, muss der optionale Wert `Nothing`, dies ist ein gültiger Wert für jeden Referenztyp. Wenn der Parameter ein Werttyp ist, muss dieses Typs einen elementaren Datentyp, der vom Visual Basic vordefiniert sein. Dies ist, da Sie ein zusammengesetzten Werttyp aufweist, z. B. eine benutzerdefinierte Struktur keine gültigen Standardwert verfügt.  
  
 Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass sie einen Verweistyp zum Vermeiden eines Werttyps verfügt über keinen gültigen Standardwert aufweist. Dies bedeutet, Sie müssen dem Typparameter entweder durch Einschränken der `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse.  
  
 **Fehler-ID:** BC32124  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Schränken Sie den Typparameter um nur den Verweistyp akzeptiert, oder verwenden Sie es nicht für den optionalen Parameter.  
  
## <a name="see-also"></a>Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Typliste](../../../visual-basic/language-reference/statements/type-list.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
