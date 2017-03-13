---
title: "checked (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "checked_CSharpKeyword"
  - "checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked-Schlüsselwort [C#]"
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# checked (C#-Referenz)
Mit dem `checked`\-Schlüsselwort wird die Überlaufprüfung für arithmetische Vorgänge und Konvertierungen mit ganzzahligen Typen explizit aktiviert.  
  
 Ausdrücke, die nur konstante Werte enthalten, verursachen standardmäßig einen Compilerfehler, wenn diese einen Wert außerhalb des Bereichs des Zieltyps erzeugen.  Wenn der Ausdruck einen oder mehrere nicht konstante Werte enthält, wird der Überlauf vom Compiler nicht erkannt.  Die Auswertung des Ausdrucks, der `i2` zugeordnet ist, im folgenden Beispiel erzeugt keinen Compilerfehler.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 Standardmäßig wird für nicht konstante Ausdrücke auch zur Laufzeit keine Überlaufprüfung durchgeführt, und es werden keine Überlaufausnahmen ausgelöst.  Im vorherigen Beispiel wird \-2,147,483,639 als Summe von zwei positiven ganzen Zahlen angezeigt.  
  
 Überlaufprüfungen können von Compileroptionen, Umgebungskonfiguration oder mit dem `checked`\-Schlüsselwort aktiviert werden.  In den folgenden Beispielen wird veranschaulicht, wie ein `checked`\-Ausdruck oder ein `checked`\-Block verwendet wird, um den Überlauf zu erkennen, der von der vorherigen Summe zur Laufzeit erzeugt wird.  In beiden Beispielen wird eine Überlaufausnahme ausgelöst.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 Mit dem [unchecked](../../../csharp/language-reference/keywords/unchecked.md)\-Schlüsselwort können Überlaufprüfungen verhindert werden.  
  
## Beispiel  
 In diesem Beispiel wird gezeigt, wie mit `checked` die Überlaufprüfung zur Laufzeit aktiviert wird.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Checked und Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)