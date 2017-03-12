---
title: "new-Einschr&#228;nkung (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new constraint-Schlüsselwort [C#]"
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# new-Einschr&#228;nkung (C#-Referenz)
Die `new`\-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration einen öffentlichen parameterlosen Konstruktor besitzen muss.  Der Typ darf nicht abstrakt sein, um die new\-Einschränkung zu verwenden.  
  
## Beispiel  
 Wenden Sie `new`\-Einschränkung auf einen Typparameter an, wenn die generische Klasse wie im folgenden Beispiel neue Instanzen des Typs erstellt:  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#5)]  
  
## Beispiel  
 Wenn Sie die `new()`\-Einschränkung mit anderen Einschränkungen verwenden, muss sie zuletzt angegeben werden:  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#6)]  
  
 Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)