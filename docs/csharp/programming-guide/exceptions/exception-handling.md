---
title: "Ausnahmebehandlung (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/09/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmebehandlung [C#], Informationen über Ausnahmebehandlung"
  - "Ausnahmen [C#], Behandlung"
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ausnahmebehandlung (C#-Programmierhandbuch)
Ein [try](../../../csharp/language-reference/keywords/try-catch.md)\-Block wird von C\#\-Programmierern verwendet, um Code zu partitionieren, der möglicherweise von einer Ausnahme betroffen ist.  Mit zugeordneten [catch](../../../csharp/language-reference/keywords/try-catch.md)\-Blöcken werden sich ergebende Ausnahmen behandelt.  Ein [finally](../../../csharp/language-reference/keywords/try-finally.md)\-Block enthält Code, der unabhängig davon ausgeführt wird, ob eine Ausnahme im `try`\-Block ausgelöst wird, z. B. Freigeben von Ressourcen, die im `try`\-Block zugeordnet werden.  Ein `try`\-Block erfordert einen oder mehrere zugeordneten `catch`\-Blöcke oder einen `finally`\-Block oder beides.  
  
 Die folgenden Beispiele zeigen eine `try-catch`\-Anweisung, eine `try-finally`\-Anweisung und eine `try-catch-finally`\-Anweisung.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 Ein `try`\-Block ohne einen `catch`\- oder `finally`\-Block verursacht einen Compilerfehler.  
  
## Catch\-Blöcke  
 Ein `catch`\-Block kann den abzufangenden Ausnahmetyp angeben.  Die Typspezifikation wird *Ausnahmefilter* genannt.  Der Ausnahmetyp muss von <xref:System.Exception> abgeleitet sein.  Geben Sie im Allgemeinen <xref:System.Exception> nicht als Ausnahmefilter an, es sei denn, Sie können alle Ausnahmen, die im `try`\-Block ausgelöst werden können, behandeln, oder Sie haben eine [throw](../../../csharp/language-reference/keywords/throw.md)\-Anweisung am Ende des `catch`\-Blocks eingefügt.  
  
 Mehrere `catch`\-Blöcke mit verschiedenen Ausnahmefiltern können miteinander verkettet werden.  Die `catch`\-Blöcke werden von oben nach unten im Code ausgewertet, aber nur ein `catch`\-Block wird für jede ausgelöste Ausnahme ausgeführt.  Der erste `catch`\-Block, der den exakten Typ oder eine Basisklasse der ausgelösten Ausnahme angibt, wird ausgeführt.  Wenn kein `catch`\-Block einen übereinstimmenden Ausnahmefilter angibt, wird ein `catch`\-Block ohne Filter ausgewählt, wenn in der Anweisung vorhanden.  Es ist wichtig, `catch`\-Blöcke mit den spezifischsten \(den am stärksten abgeleiteten\) Ausnahmetypen zuerst zu positionieren.  
  
 Sie sollten Ausnahmen abfangen, wenn die folgenden Bedingungen gelten:  
  
-   Sie haben ausreichende Kenntnisse darüber, aus welchem Grund die Ausnahme ausgelöst werden kann, und Sie können eine bestimmte Wiederherstellung implementieren, z. B. Auffordern des Benutzers, einen neuen Dateinamen einzugeben, wenn Sie ein <xref:System.IO.FileNotFoundException>\-Objekt abfangen.  
  
-   Sie können eine neue und spezifischere Ausnahme erstellen und auslösen.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   Sie möchten eine Ausnahme teilweise behandeln, bevor Sie diese für zusätzliche Behandlung übergeben.  Im folgenden Beispiel wird ein `catch`\-Block verwendet, um einen Eintrag einem Fehlerprotokoll hinzuzufügen, bevor die Ausnahme erneut ausgelöst wird.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## Finally\-Blöcke  
 Mithilfe eines `finally`\-Blocks können Sie Aktionen bereinigen, die in einem `try`\-Block ausgeführt werden.  Falls vorhanden, wird der `finally`\-Block zuletzt ausgeführt wird, nach dem `try`\-Block und einem entsprechenden `catch`\-Block.  Unabhängig davon, ob eine Ausnahme ausgelöst wurde oder ein mit dem Ausnahmetyp übereinstimmender `catch`\-Block gefunden wurde, wird ein `finally`\-Block immer ausgeführt.  
  
 Der `finally`\-Block kann verwendet werden, um Ressourcen wie Dateistreams, Datenbankverbindungen und Grafikhandles freizugeben, ohne darauf zu warten, dass der Garbage Collector Objekte in der Laufzeit abschließt.  Weitere Informationen finden Sie unter [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Im folgenden Beispiel wird der `finally`\-Block verwendet, um eine Datei zu schließen, die im `try`\-Block geöffnet wurde.  Beachten Sie, dass vor dem Schließen der Datei der Zustand des Dateihandles überprüft wird.  Wenn der `try`\-Block die Datei nicht öffnen kann, hat das Dateihandle weiterhin den Wert `null`, und der `finally`\-Block versucht nicht, sie zu schließen.  Wenn alternativ dazu die Datei erfolgreich im `try`\-Block geöffnet wird, schließt der `finally`\-Block die geöffnete Datei.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)