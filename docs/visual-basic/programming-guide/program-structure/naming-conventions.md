---
title: "Visual Basic Naming Conventions | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "names, Visual Basic rules"
  - "naming conventions"
  - "naming conventions, Visual Basic"
  - "Visual Basic code, naming conventions"
  - "conventions, Visual Basic coding"
  - "names, naming conventions"
  - "naming conventions, classes"
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Visual Basic Naming Conventions
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie ein Element in einer Visual Basic\-Anwendung benennen, muss das erste Zeichen dieses Namens ein alphabetisches Zeichen oder ein Unterstrich sein.  Beachten Sie jedoch, dass mit einem Unterstrich beginnende Namen nicht mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel sind.  
  
 Für die Benennung von Elementen gelten folgende Empfehlungen:  
  
-   Beginnen Sie jedes einzelne Wort in einem Namen mit einem Großbuchstaben, wie in `FindLastRecord` oder `RedrawMyForm`.  
  
-   Beginnen Sie Funktions\- und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.  
  
-   Beginnen Sie Namen von Klassen, Strukturen, Modulen und Eigenschaften mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory`.  
  
-   Beginnen Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem substantivischen Begriff, wie in `IComponent`, oder mit einem Adjektiv, das das Schnittstellenverhalten beschreibt, z. B. `IPersistable`.  Verwenden Sie nicht den Unterstrich, und setzen Sie möglichst wenige Abkürzungen ein, da diese zu Missverständnissen führen können.  
  
-   Beginnen Sie die Namen von Ereignishandlern mit einem Substantiv, das den Typ des Ereignisses beschreibt, auf das das Suffix `EventHandler` folgt, wie in `MouseEventHandler`.  
  
-   Verwenden Sie für die Namen von Ereignisargumentklassen das Suffix `EventArgs`.  
  
-   Wenn ein Ereignis ein Konzept von "davor" oder "danach" aufweist, verwenden Sie ein Suffix im Präsens oder in der Vergangenheit, wie in "`ControlAdd`" oder "`ControlAdded`".  
  
-   Verwenden Sie für lange oder oft verwendete Ausdrücke Abkürzungen, um die Namen möglichst kurz zu halten, z. B. "HTML" statt "Hypertext Markup Language".  Grundsätzlich sind Variablennamen, die länger als 32 Zeichen sind, auf einem Bildschirm mit niedriger Auflösung schwer zu lesen.  Verwenden Sie außerdem in der gesamten Anwendung einheitliche Abkürzungen.  Wenn Sie z. B. in einem Projekt sowohl "HTML" als auch "Hypertext Markup Language" schreiben, kann dies zu Verwirrung führen.  
  
-   Verwenden Sie in einem inneren Gültigkeitsbereich nicht die gleichen Namen wie in einem äußeren Gültigkeitsbereich.  Wenn auf die falsche Variable zugegriffen wird, können Fehler auftreten.  Im Falle eines Konflikts zwischen einer Variablen und dem Schlüsselwort gleichen Namens müssen Sie das Schlüsselwort identifizieren, indem Sie davor die entsprechende Typbibliothek angeben.  Wenn Sie eine Variable beispielsweise `Date` genannt haben, können Sie die systeminterne Funktion `Date` nur noch mithilfe von <xref:System.DateTime.Date%2A?displayProperty=fullName> aufrufen.  
  
## Siehe auch  
 [Keywords as Element Names in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)