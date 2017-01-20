---
title: "Procedures in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, structured code"
  - "Visual Basic code, procedures"
  - "procedures, types of"
  - "structured code, procedures"
  - "procedures"
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedures in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine *Prozedur* ist ein Block von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Anweisungen, die von einer Deklarationsanweisung \(`Function`, `Sub`, `Operator`, `Get`, `Set`\) und einer übereinstimmenden `End`\-Deklaration eingeschlossen wird.  Alle ausführbaren Anweisungen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] müssen in einer Prozedur enthalten sein.  
  
## Aufrufen einer Prozedur  
 Prozeduren werden an anderer Stelle im Code aufgerufen.  Dieser Vorgang wird als *Prozeduraufruf* bezeichnet.  Wenn die Prozedur ausgeführt wurde, wird die Steuerung an den Code zurückgegeben, der die Prozedur aufgerufen hat. Dieser Code wird als *aufrufender Code* bezeichnet.  Der Aufrufcode ist eine Anweisung oder ein Ausdruck in einer Anweisung. Er gibt die Prozedur anhand ihres Namens an und übergibt die Steuerung an die Prozedur.  
  
## Beenden einer Prozedur  
 Eine Prozedur gibt die Steuerung an den aufrufenden Code zurück, wenn ihre Ausführung beendet wurde.  Hierzu kann sie eine [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), die entsprechende [Exit Statement](../../../../visual-basic/language-reference/statements/exit-statement.md)\-Anweisung für die Prozedur oder die [End \<keyword\> Statement](../../../../visual-basic/language-reference/statements/end-keyword-statement.md)\-Anweisung der Prozedur verwenden.  Die Steuerung wird dann an den aufrufenden Code nach dem Code des Prozeduraufrufs übergeben.  
  
-   Bei einer `Return`\-Anweisung kehrt die Steuerung direkt an den aufrufenden Code zurück.  Anweisungen nach der `Return`\-Anweisung werden nicht ausgeführt.  Die gleiche Prozedur kann mehrere `Return`\-Anweisungen enthalten.  
  
-   Bei einer `Exit Sub`\-Anweisung oder einer `Exit Function`\-Anweisung kehrt die Steuerung direkt an den aufrufenden Code zurück.  Anweisungen nach der `Exit`\-Anweisung werden nicht ausgeführt.  Eine Prozedur kann mehrere `Exit`\-Anweisungen enthalten, und Sie können `Return`\-Anweisungen sowie `Exit`\-Anweisungen in einer Prozedur gleichzeitig verwenden.  
  
-   Wenn eine Prozedur keine `Return`\-Anweisung oder `Exit`\-Anweisung enthält, wird sie mit einer `End Sub`\-Anweisung oder einer `End Function`\-Anweisung bzw. mit einer `End Get`\-Anweisung oder einer `End Set`\-Anweisung nach der letzten Anweisung des Prozedurtexts beendet.  Die `End`\-Anweisung gibt die Steuerung sofort an den aufrufenden Code zurück.  Eine Prozedur darf nur eine einzige `End`\-Anweisung enthalten.  
  
## Parameter und Argumente  
 In den meisten Fällen muss eine Prozedur bei jedem Aufruf auf andere Daten angewendet werden.  Sie können diese Informationen im Rahmen des Prozeduraufrufs an die Prozedur übergeben.  Die Prozedur definiert 0 \(null\) oder mehr *Parameter*, von denen jeder einen Wert darstellt, der an die Prozedur übergeben werden soll.  Jedem Parameter in der Prozedurdefinition entspricht ein *Argument* im Prozeduraufruf.  Ein Argument stellt den Wert dar, den Sie in einem bestimmten Prozeduraufruf an den entsprechenden Parameter übergeben.  
  
## Prozedurtypen  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] werden verschiedene Prozedurtypen verwendet:  
  
-   [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) führen Aktionen aus, geben jedoch keinen Wert an den aufrufenden Code zurück.  
  
-   Ereignisbehandlungsprozeduren sind `Sub`\-Prozeduren, die als Reaktion auf ein durch eine Benutzeraktion ausgelöstes Ereignis oder ein Ereignis im Programm ausgeführt werden.  
  
-   [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) geben einen Wert an den aufrufenden Code zurück.  Sie können weitere Aktionen ausführen, bevor sie beendet werden.  
  
-   [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) geben Eigenschaftswerte an Objekte oder Module zurück und weisen sie diesen zu.  
  
-   [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) definieren das Verhalten eines Standardoperators, wenn es sich bei einem oder beiden Operanden um eine neu definierte Klasse oder Struktur handelt.  
  
-   [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) definieren zusätzlich zu ihren normalen Parametern einen oder mehrere *Typparameter*, sodass der aufrufende Code bei jedem Aufruf bestimmte Datentypen übergeben kann.  
  
## Prozeduren und strukturierter Code  
 Jede Zeile im ausführbaren Code einer Anwendung muss in einer Prozedur, z. B. `Main`, `calculate` oder `Button1_Click`, enthalten sein.  Sie sollten umfangreiche Prozeduren in kleinere unterteilen, damit die Anwendung leichter lesbar ist.  
  
 Prozeduren eignen sich zur Ausführung von sich wiederholenden oder freigegebenen Aufgaben, wie häufig verwendeten Berechnungen, Text\- und Steuerelementänderungen sowie Datenbankoperationen.  Prozeduren können von vielen unterschiedlichen Stellen im Code aus aufgerufen werden, d. h., sie können als Bausteine der Anwendung verwendet werden.  
  
 Den Code mit Prozeduren zu strukturieren bietet folgende Vorteile:  
  
-   Prozeduren ermöglichen es Ihnen, das Programm in einzelne logische Einheiten zu unterteilen.  Einzelne Einheiten sind wesentlich einfacher zu debuggen als ein gesamtes Programm ohne Prozeduren.  
  
-   Nachdem Sie Prozeduren für ein bestimmtes Programm entwickelt haben, können Sie sie auch in anderen Programmen verwenden. Hierzu sind häufig nur geringfügige oder überhaupt keine Änderungen erforderlich.  Dies erleichtert die Vermeidung von Codeduplikaten.  
  
## Siehe auch  
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)