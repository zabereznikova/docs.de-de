---
title: Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 273ea592e73be5d76a4ffef077e691014a108347
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402926"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
Eine Prozedur wird mit einem optionalen Parameter deklariert, der einen Typparameter verwendet, der nicht als Referenztyp beschränkt ist.  
  
 Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben. Wenn der-Parameter ein Verweistyp ist, muss der optionale Wert lauten `Nothing` . Dies ist ein gültiger Wert für einen beliebigen Verweistyp. Wenn es sich bei dem Parameter jedoch um einen Werttyp handelt, muss es sich bei dem Typ um einen vom Visual Basic vordefinierten elementaren Datentyp handeln. Dies liegt daran, dass ein zusammengesetzter Werttyp, z. b. eine benutzerdefinierte Struktur, über keinen gültigen Standardwert verfügt.  
  
 Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass es sich um einen Verweistyp handelt, um die Möglichkeit eines Werttyps ohne gültigen Standardwert zu vermeiden. Dies bedeutet, dass Sie den Typparameter entweder mit dem- `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse einschränken müssen.  
  
 **Fehler-ID:** BC32124  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Schränken Sie den Typparameter ein, um nur einen Verweistyp zu akzeptieren, oder verwenden Sie ihn nicht für den optionalen Parameter.  
  
## <a name="see-also"></a>Weitere Informationen

- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
- [Class-Anweisung](../statements/class-statement.md)
- [Optionale Parameter](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Schweigen](../nothing.md)
