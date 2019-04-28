---
title: Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802325"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
Eine Prozedur ist mit einem optionalen Parameter deklariert, die einen Typparameter verwendet, der nicht zu einem Referenztyp eingeschränkt wird.  
  
 Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben. Wenn der Parameter eines Verweistyps ist, muss der optionale Wert `Nothing`, dies ist ein gültiger Wert für jeden Referenztyp. Wenn der Parameter einen Werttyp ist, muss dieses Typs jedoch ein elementarer Datentyp, der von Visual Basic vordefiniert sein. Dies ist da ein zusammengesetzten Werttyp, z. B. eine benutzerdefinierte Struktur, die keinen gültigen Standardwert verfügt.  
  
 Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass es ein Verweistyp, vermeiden Sie die Möglichkeit, einen Werttyp besitzt keinen gültigen Standardwert handelt. Dies bedeutet, Sie müssen dem Typparameter einschränken, entweder mit der `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse.  
  
 **Fehler-ID:** BC32124  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Einschränken Sie den Typparameter nur den Verweistyp akzeptiert, oder verwenden Sie es nicht für den optionalen Parameter.  
  
## <a name="see-also"></a>Siehe auch

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
