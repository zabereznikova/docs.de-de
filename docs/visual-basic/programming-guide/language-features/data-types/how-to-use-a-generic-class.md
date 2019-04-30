---
title: 'Vorgehensweise: Verwenden einer generischen Klasse (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: c7fb4c95b6ef09508df57b3a0c08a651b122e251
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906476"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Vorgehensweise: Verwenden einer generischen Klasse (Visual Basic)
Eine Klasse, die *Typparameter* akzeptiert, wird *generische Klasse*genannt. Wenn Sie eine generische Klasse verwenden, können Sie daraus eine *erzeugte Klasse* generieren, indem Sie ein *Typargument* für jeden dieser Parameter angeben. Sie können dann eine Variable vom Typ der erzeugten Klasse deklarieren, und Sie können eine Instanz der erzeugten Klasse erstellen und dieser Variablen zuweisen.  
  
 Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.  
  
 Beim folgenden Verfahren wird eine generische Klasse verwendet, die in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] definiert ist, und eine Instanz daraus erstellt.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Eine Klasse verwenden, die einen Typparameter braucht  
  
1. Fügen Sie am Anfang der Quelldatei, eine [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zum Importieren der <xref:System.Collections.Generic?displayProperty=nameWithType> Namespace. Dadurch können Sie auf die <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>-Klasse verweisen, ohne sie zur Unterscheidung von anderen Warteschlangenklassen wie z.B. <xref:System.Collections.Queue?displayProperty=nameWithType> vollständig qualifizieren zu müssen.  
  
2. Erstellen Sie das Objekt, auf die übliche Weise, aber fügen `(Of type)` sofort nach dem Klassennamen.  
  
     Im folgenden Beispiel wird dieselbe Klasse (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) verwendet, um zwei Warteschlangenobjekte zu erstellen, die Artikel mit unterschiedlichen Datentypen enthalten. Es fügt Elemente am Ende jeder Warteschlange ein und entfernt und zeigt Elemente am Beginn jeder Warteschlange.  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md)
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Iteratoren](../../../../visual-basic/programming-guide/concepts/iterators.md)
