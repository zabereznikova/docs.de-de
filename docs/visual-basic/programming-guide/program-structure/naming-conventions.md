---
title: Benennungskonventionen
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347312"
---
# <a name="visual-basic-naming-conventions"></a>Benennungskonventionen in Visual Basic
Wenn Sie ein Element in der Visual Basic Anwendung benennen, muss das erste Zeichen dieses Namens ein alphabetisches Zeichen oder ein Unterstrich sein. Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen, nicht mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel sind.  
  
 Die folgenden Vorschläge gelten für die Benennung.  
  
- Beginnen Sie jedes einzelne Wort in einem Namen mit einem Großbuchstaben, wie in `FindLastRecord` und `RedrawMyForm`.  
  
- Beginnen Sie Funktions-und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.  
  
- Beginnen Sie Klassen-, Struktur-, Modul-und Eigenschaftsnamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory`.  
  
- Starten Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem Substantiv Ausdruck, wie z. b. `IComponent`, oder mit einem Adjektiv, das das Verhalten der Schnittstelle beschreibt, wie `IPersistable`. Verwenden Sie den Unterstrich nicht, und verwenden Sie Abkürzungen sparsam, da Abkürzungen Verwirrung verursachen können.  
  
- Beginnen Sie die Namen von Ereignis Handlern mit einem Substantiv, das den Ereignistyp, gefolgt vom Suffix "`EventHandler`", wie in "`MouseEventHandler`" beschreibt.  
  
- Fügen Sie in Namen von Ereignis Argument Klassen das Suffix "`EventArgs`" ein.  
  
- Wenn ein Ereignis das Konzept "Before" oder "After" hat, verwenden Sie ein Suffix in der Vergangenheit oder Vergangenheitsform, wie in "`ControlAdd`" oder "`ControlAdded`".  
  
- Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen, um die namens Längen angemessen zu halten, z. b. "HTML" anstelle von "Hypertext Markup Language". Im Allgemeinen ist es schwierig, Variablennamen mit mehr als 32 Zeichen auf einem Monitor zu lesen, der auf eine niedrige Auflösung festgelegt ist. Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung einheitlich sind. Das zufällige wechseln in ein Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.  
  
- Vermeiden Sie die Verwendung von Namen in einem inneren Gültigkeitsbereich, die mit Namen in einem äußeren Gültigkeitsbereich identisch sind. Fehler können auftreten, wenn auf die falsche Variable zugegriffen wird. Wenn zwischen einer Variablen und dem Schlüsselwort mit demselben Namen ein Konflikt auftritt, müssen Sie das Schlüsselwort identifizieren, indem Sie es der entsprechenden Typbibliothek vorangestellt haben. Wenn Sie z. b. eine Variable namens `Date`haben, können Sie die intrinsische `Date` Funktion nur durch Aufrufen von <xref:System.DateTime.Date%2A?displayProperty=nameWithType>verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter als Elementnamen in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)
