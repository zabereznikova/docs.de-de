---
title: "Zugriffsdom&#228;ne (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zugriffsdomäne [C#]"
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Zugriffsdom&#228;ne (C#-Referenz)
Die Zugriffsdomäne eines Members gibt an, in welchen Programmabschnitten auf einen Member verwiesen werden kann.  Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl von der [Zugriffsebene](../../../csharp/language-reference/keywords/accessibility-levels.md) des Members als auch von der Zugriffsdomäne des unmittelbar enthaltenden Typs bestimmt.  
  
 Die Zugriffsdomäne eines Typs der obersten Ebene enthält mindestens den Programmtext des Projekts, in dem er deklariert wurde.  Das heißt, die Domäne enthält alle Quelldateien dieses Projekts.  Die Zugriffsdomäne eines geschachtelten Typs beinhaltet mindestens den Programmtext des Typs, in dem er deklariert wurde.  Das bedeutet, dass die Domäne der Typtext ist, der alle geschachtelten Typen einschließt.  Die Zugriffsdomäne eines geschachtelten Typs geht nie über die Zugriffsdomäne des enthaltenden Typs hinaus.  Die Konzepte werden im nachstehenden Beispiel demonstriert.  
  
## Beispiel  
 Dieses Beispiel beinhaltet einen Typ der obersten Ebene, `T1`, und zwei geschachtelte Klassen, `M1` und `M2`.  Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen.  Bei der `Main`\-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt.  Beachten Sie, dass die Anweisungen, die auf die nicht zugreifbaren Member verweisen, auskommentiert sind.  Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf nicht zugreifbare Member verursacht werden, entfernen Sie jeden Kommentar einzeln.  
  
 [!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)