---
title: "Gewusst wie: Behandeln einer Ausnahme mit try/catch (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmebehandlung [C#], try/catch-Blöcke"
  - "Ausnahmen [C#], try/catch-Blöcke"
  - "try/catch-Blöcke [C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Gewusst wie: Behandeln einer Ausnahme mit try/catch (C#-Programmierhandbuch)
Der Zweck eines [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)\-Blocks ist das Abfangen und Behandeln einer Ausnahme, die durch Arbeitscode generiert wurde.  Einige Ausnahmen können in einem `catch`\-Block behandelt werden, sodass das Problem behoben ist und die Ausnahme nicht wieder ausgelöst wird. Meistens können Sie jedoch nur sicherstellen, dass eine passendere Ausnahme ausgelöst wird.  
  
## Beispiel  
 In diesem Beispiel ist <xref:System.IndexOutOfRangeException> nicht die geeignetste Ausnahme: <xref:System.ArgumentOutOfRangeException> ist für die Methode sinnvoller, da der Fehler durch das vom Aufrufer übergebene `index`\-Argument verursacht wird.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/csharp/how-to-handle-an-excepti_1.cs)]  
  
## Kommentare  
 Der Code, der eine Ausnahme auslöst, ist im `try`\-Block eingeschlossen.  Eine `catch`\-Anweisung wird unmittelbar anschließend hinzugefügt, um `IndexOutOfRangeException` zu behandeln, wenn sie auftritt.  Der `catch`\-Block behandelt die `IndexOutOfRangeException` und löst stattdessen die passendere `ArgumentOutOfRangeException`\-Ausnahme aus.  Um dem Aufrufer möglichst viele Informationen bereitzustellen, sollten Sie die ursprüngliche Ausnahme als <xref:System.Exception.InnerException%2A> der neuen Ausnahme angeben.  Da die <xref:System.Exception.InnerException%2A>\-Eigenschaft [schreibgeschützt](../../../csharp/language-reference/keywords/readonly.md) ist, müssen Sie sie im Konstruktor der neuen Ausnahme zuweisen.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)