---
title: <expression> kann nicht als Typeinschränkung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 8dbf510d7c6ee80e2dcd2f9d2552bc870413cbab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838104"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a>"\<Ausdruck >' kann nicht als typeinschränkung verwendet werden
Eine Einschränkungsliste enthält einen Ausdruck, der keine gültige Einschränkung für einen Typparameter darstellt.  
  
 Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird. Sie können die folgenden Anforderungen in beliebiger Kombination angeben:  
  
-   Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
-   Das Typargument darf von höchstens einer Klasse erben.  
  
-   Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann (die `New` -Einschränkung muss enthalten sein)  
  
 Wenn Sie keine bestimmte Klasse oder Schnittstelle in die Einschränkungsliste aufnehmen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Festlegungen treffen:  
  
-   Das Typargument muss ein Werttyp sein (die Einschränkung `Structure` enthalten)  
  
-   Das Typargument muss ein Verweistyp sein (die Einschränkung `Class` enthalten)  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler-ID:** BC32061  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass der Ausdruck und dessen Elemente richtig geschrieben sind.  
  
-   Wenn der Ausdruck die Anforderungen der vorangehenden Liste nicht erfüllt, entfernen Sie ihn aus der Einschränkungsliste.  
  
-   Wenn der Ausdruck auf eine Schnittstelle oder Klasse verweist, stellen Sie sicher, dass der Compiler Zugriff auf diese Schnittstelle oder Klasse hat. Möglicherweise müssen Sie deren Namen qualifizieren und einen Verweis auf Ihr Projekt hinzufügen. Weitere Informationen finden Sie unter "Verweise auf Projekte" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Siehe auch

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
