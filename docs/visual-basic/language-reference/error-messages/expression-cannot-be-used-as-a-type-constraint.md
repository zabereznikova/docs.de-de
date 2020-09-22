---
title: <expression> kann nicht als Typeinschränkung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 4f1db6bdbe6f25d0362b55acd95e716fbc2417ed
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874275"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a>\<expression> kann nicht als Typeinschränkung verwendet werden.

Eine Einschränkungsliste enthält einen Ausdruck, der keine gültige Einschränkung für einen Typparameter darstellt.  
  
 Eine Einschränkungsliste erzwingt Anforderungen für das Typargument, das an den Typparameter übergeben wird. Sie können die folgenden Anforderungen in beliebiger Kombination angeben:  
  
- Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
- Das Typargument darf von höchstens einer Klasse erben.  
  
- Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann (die `New` -Einschränkung muss enthalten sein)  
  
 Wenn Sie keine bestimmte Klasse oder Schnittstelle in die Einschränkungsliste aufnehmen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Festlegungen treffen:  
  
- Das Typargument muss ein Werttyp sein (die Einschränkung `Structure` enthalten)  
  
- Das Typargument muss ein Verweistyp sein (die Einschränkung `Class` enthalten)  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler-ID:** BC32061  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass der Ausdruck und dessen Elemente richtig geschrieben sind.  
  
- Wenn der Ausdruck die Anforderungen der vorangehenden Liste nicht erfüllt, entfernen Sie ihn aus der Einschränkungsliste.  
  
- Wenn der Ausdruck auf eine Schnittstelle oder Klasse verweist, stellen Sie sicher, dass der Compiler Zugriff auf diese Schnittstelle oder Klasse hat. Möglicherweise müssen Sie deren Namen qualifizieren und einen Verweis auf Ihr Projekt hinzufügen. Weitere Informationen finden Sie unter "Verweise auf Projekte" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Wert- und Verweistypen](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
