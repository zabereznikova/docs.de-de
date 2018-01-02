---
title: "Benennungskonventionen in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97f02fd85d4796d6799a8a5b40a9137eeb79a93f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="visual-basic-naming-conventions"></a>Benennungskonventionen in Visual Basic
Wenn Sie ein Element in Visual Basic-Anwendung benennen, muss das erste Zeichen des Namens ein alphabetisches Zeichen oder ein Unterstrich sein. Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen nicht mit kompatibel sind die [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Die folgenden Vorschläge gelten für die Benennung.  
  
-   Jedes einzelne Wort in einem Namen mit einem Großbuchstaben beginnen, wie in `FindLastRecord` und `RedrawMyForm`.  
  
-   BEGIN-Funktion und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.  
  
-   BEGIN-Klasse, Struktur, Modul und Eigenschaftennamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory`.  
  
-   Beginnen Sie Schnittstellennamen mit dem Präfix "I", gefolgt von ein Nomen oder ein nominaler Ausdruck, z. B. `IComponent`, oder mit einem Adjektiv, beschreibt das Schnittstellenverhalten, z. B. `IPersistable`. Keine des Unterstrich, und nutzen verwenden Sie Abkürzungen sparsam und nur dann, da Abkürzungen zu Verwirrung führen können.  
  
-   Beginnen Sie Ereignishandlernamen mit einem Nomen beschreibt den Typ des Ereignisses, gefolgt von der "`EventHandler`"-Suffix enthält, wie in"`MouseEventHandler`".  
  
-   Namen von Ereignisargumentklassen, enthalten die "`EventArgs`" Suffix.  
  
-   Wenn ein Ereignis ein Konzept von "before" oder "after" aufweist, verwenden Sie ein Suffix in Gegenwarts- oder Vergangenheitsform, wie in "`ControlAdd`"oder"`ControlAdded`".  
  
-   Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen um Namen Längen angebracht ist, behalten Sie z. B. "HTML", anstelle von "Hypertext Markup Language". Im Allgemeinen sind Variablennamen, die größer als 32 Zeichen schwer zu lesen, auf einem Bildschirm mit niedriger Auflösung. Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung konsistent sind. Wechseln nach dem Zufallsprinzip in einem Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.  
  
-   Vermeiden Sie Namen in einem inneren Gültigkeitsbereich, die den Namen in einem äußeren Gültigkeitsbereich identisch sind. Fehler können auftreten, wenn die falsche Variable zugegriffen wird. Wenn ein Konflikt zwischen einer Variablen und das Schlüsselwort mit dem gleichen Namen ausgeführt wird, müssen Sie das Schlüsselwort es mit der entsprechenden Typbibliothek abgrenzen, indem Sie identifizieren. Angenommen, Sie haben eine Variable namens `Date`, können Sie die systeminterne Funktion `Date` Funktion nur über einen Aufruf <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter als Elementnamen in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)
