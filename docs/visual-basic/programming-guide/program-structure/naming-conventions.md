---
title: Benennungskonventionen in Visual Basic
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
ms.openlocfilehash: ebb9d21e32993f2eb035993d32dc3de7d97b49f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672135"
---
# <a name="visual-basic-naming-conventions"></a>Benennungskonventionen in Visual Basic
Wenn Sie ein Element in Visual Basic-Anwendung benennen, muss das erste Zeichen des Namens ein alphabetisches Zeichen oder einem Unterstrich sein. Beachten Sie jedoch, dass die Namen, die mit einem Unterstrich beginnen mit nicht konform sind die [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Die folgenden Vorschläge gelten für die Benennung.  
  
-   Jedes einzelne Wort in einem Namen mit einem Großbuchstaben beginnen, wie in `FindLastRecord` und `RedrawMyForm`.  
  
-   Beginnen Sie-Funktion und Methode mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.  
  
-   BEGIN-Klasse, Struktur, Modul und Eigenschaftennamen mit einem Substantiv bestehen, wie in `EmployeeName` oder `CarAccessory`.  
  
-   Beginnen Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem nominalen Ausdruck, z. B. `IComponent`, oder mit einem Adjektiv, beschreibt das Schnittstellenverhalten, wie z. B. `IPersistable`. Nicht verwenden den Unterstrich und Abkürzungen sparsam und nur dann verwendet werden, da Abkürzungen verwirrend sein können.  
  
-   Beginnen Sie mit einem Substantiv, beschreibt den Typ des Ereignisses, gefolgt von Ereignishandlernamen der "`EventHandler`"-Suffix enthält, wie in"`MouseEventHandler`".  
  
-   Die Namen der Ereignisargumentklassen enthalten die "`EventArgs`" Suffix.  
  
-   Wenn ein Ereignis ein Konzept der "before" oder "after" aufweist, verwenden Sie ein Suffix in Gegenwarts- oder Vergangenheitsform, wie in "`ControlAdd`"oder"`ControlAdded`".  
  
-   Verwenden Sie für lang oder häufig verwendete Begriffe Abkürzungen um Namen Längen sinnvoll zu begrenzen, z. B. "HTML", anstelle von "Hypertext Markup Language". Im Allgemeinen die Variablennamen, die größer als 32 Zeichen sind schwer zu lesen, auf einem Monitor mit niedriger Auflösung. Stellen Sie außerdem sicher, dass Ihre Abkürzungen in der gesamten Anwendung einheitlich sind. Wechseln nach dem Zufallsprinzip in einem Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.  
  
-   Vermeiden Sie Namen in einem inneren Gültigkeitsbereich, die den Namen in einem äußeren Bereich identisch sind. Wenn die falsche Variable zugegriffen wird, können zu einem Fehler führen. Im Falle ein Konflikts zwischen einer Variablen und das Schlüsselwort mit demselben Namen müssen Sie das Schlüsselwort es mit der entsprechenden Typbibliothek abgrenzen, indem Sie identifizieren. Angenommen, Sie haben eine Variable namens `Date`, können Sie die systeminterne Funktion `Date` Funktion nur über einen Aufruf <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- [Schlüsselwörter als Elementnamen in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)
