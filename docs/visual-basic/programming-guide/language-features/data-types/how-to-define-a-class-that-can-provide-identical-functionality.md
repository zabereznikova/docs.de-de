---
title: 'Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 3b1f47250453c32735d633b98da0bd0ddb1ed5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393856"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann (Visual Basic)
Sie können eine Klasse definieren, über die Sie Objekte erstellen können, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen. Hierzu geben Sie in der Definition mindestens einen *Typparameter* an. Die Klasse kann dann als Vorlage für Objekte fungieren, für die verschiedene Datentypen verwendet werden. Eine in dieser Weise definierte Klasse wird als *generische Klasse*bezeichnet.  
  
 Der Vorteil des Definierens einer generischen Klasse besteht darin, dass Sie die Klasse nur einmal definieren müssen und diese in Ihrem Code verwenden können, um viele Objekte zu erstellen, für die unterschiedliche Datentypen verwendet werden. Dies führt zu einer besseren Leistung, als dies der Fall ist, wenn die Klasse mit dem `Object` -Typ definiert wird.  
  
 Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>So definieren Sie eine Klasse mit einem Typparameter  
  
1. Definieren Sie die Klasse auf die übliche Weise.  
  
2. Fügen Sie `(Of` *typeparameter* `)` unmittelbar nach dem Klassennamen hinzu, um einen Typparameter anzugeben.  
  
3. Sind mehrere Typparameter vorhanden, erstellen Sie innerhalb der Klammern eine Liste mit Kommas als Trennzeichen. Geben Sie das `Of` -Schlüsselwort nur einmal an.  
  
4. Werden im Code Operationen für einen Typparameter ausgeführt, die über eine einfache Zuweisung hinausgehen, geben Sie nach dem Typparameter eine `As` -Klausel an, um die entsprechende Anzahl von *Einschränkungen*hinzuzufügen. Eine Einschränkung gewährleistet, dass der für den Typparameter angegebene Typ eine Anforderung erfüllt, beispielsweise eine der folgenden:  
  
    - Unterstützt eine Operation, etwa `>`, die der Code ausführt  
  
    - Unterstützt einen Member, etwa eine Methode, auf den der Code zugreift  
  
    - Macht einen parameterlosen Konstruktor verfügbar  
  
     Wenn Sie keine Einschränkungen angeben, können im Code nur Operationen und Member verwendet werden, die vom [Object Data Type](../../../language-reference/data-types/object-data-type.md)unterstützt werden. Weitere Informationen finden Sie unter [Type List](../../../language-reference/statements/type-list.md).  
  
5. Identifizieren Sie jeden Klassenmember, der mit einem bereitgestellten Typ deklariert werden soll, und deklarieren Sie ihn `As` `typeparameter` . Dies gilt für die interne Speicherung, für Prozedurparameter und für Rückgabewerte.  
  
6. Im Code dürfen nur Operationen und Methoden verwenden, die von jedem Datentyp unterstützt werden, der im Code für `itemType`angegeben werden kann.  
  
     Im folgenden Beispiel wird eine Klasse definiert, in der eine sehr einfache Liste verwaltet wird. Die Klasse speichert die Liste im internen Array `items`, und der verwendende Code kann den Datentyp der Listenelemente deklarieren. Mit einem parametrisierten Konstruktor kann der Using-Code die obere Grenze von festlegen `items` , und der Parameter lose Konstruktor legt diese auf 9 (für insgesamt 10 Elemente) fest.  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     Sie können eine Klasse aus `simpleList` deklarieren, die eine Liste von `Integer` -Werten enthält, eine andere Klasse, die eine Liste von `String` -Werten enthält, und eine weitere Klasse, die `Date` -Werte enthält. Abgesehen vom Datentyp der Listenmember verhalten sich Objekte, die aus einer dieser Klassen erstellt wurden, gleich.  
  
     Das Typargument, das im verwendenden Code für `itemType` bereitgestellt wird, kann ein systeminterner Typ, etwa `Boolean` oder `Double`, eine Struktur, eine Enumeration oder ein beliebiger Klassentyp sein, einschließlich eines in der Anwendung definierten Klassentyps.  
  
     Sie können die Klasse `simpleList` mit dem folgenden Code testen.  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypen](index.md)
- [Generische Typen in Visual Basic (Visual Basic)](generic-types.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md)
- [Natürlich](../../../language-reference/statements/of-clause.md)
- [Type List](../../../language-reference/statements/type-list.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](how-to-use-a-generic-class.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
