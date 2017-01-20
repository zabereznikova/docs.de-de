---
title: "unchecked (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unchecked_CSharpKeyword"
  - "unchecked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unchecked-Schlüsselwort [C#]"
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# unchecked (C#-Referenz)
Das `unchecked`\-Schlüsselwort wird verwendet, um die Überlaufprüfung für arithmetische Operationen und Konvertierungen mit ganzzahligen Typen zu unterdrücken.  
  
 Wenn ein Ausdruck in einem nicht geprüften Kontext einen Wert erzeugt, der außerhalb des Gültigkeitsbereichs des Zieltyps liegt, wird der Überlauf nicht gekennzeichnet.  Da die Berechnung beispielsweise in einem `unchecked`\-Block oder \-Ausdruck erfolgt, wird die Tatsache ignoriert, dass das Ergebnis zu groß für eine ganze Zahl ist, und `int1` wird der Wert \-2,147,483,639 zugewiesen.  
  
 [!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 Wenn die `unchecked`\-Umgebung entfernt wird, tritt ein Kompilierungsfehler auf.  Der Überlauf kann zur Kompilierzeit erkannt werden, da alle Begriffe des Ausdrucks Konstanten sind.  
  
 Ausdrücke, die nicht konstante Begriffe enthalten, werden zur Kompilierzeit sowie zur Laufzeit standardmäßig deaktiviert.  Informationen zum Aktivieren einer überprüften Umgebung finden Sie unter [checked](../../../csharp/language-reference/keywords/checked.md).  
  
 Da die Überlaufprüfung einige Zeit in Anspruch nimmt, kann die Leistung durch die Verwendung von deaktiviertem Code verbessert werden, wenn keine Gefahr eines Überlaufs besteht.  Wenn Überläufe jedoch möglich sind, sollte eine überprüfte Umgebung verwendet werden.  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie das `unchecked`\-Schlüsselwort verwendet wird.  
  
 [!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Checked und Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [checked](../../../csharp/language-reference/keywords/checked.md)