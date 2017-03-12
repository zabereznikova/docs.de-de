---
title: "Gewusst wie: Initialisieren eines W&#246;rterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Auflistungsinitialisierer [C#], Wörterbuch"
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# Gewusst wie: Initialisieren eines W&#246;rterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)
Ein <xref:System.Collections.Generic.Dictionary%602> enthält eine Auflistung von Schlüssel\/Wert\-Paaren.  Die <xref:System.Collections.Generic.Dictionary%602.Add%2A>\-Methode basiert auf zwei Parametern: ein Parameter für den Schlüssel und der andere für den Wert.  Um ein <xref:System.Collections.Generic.Dictionary%602> oder eine andere Auflistung, deren `Add`\-Methode mehrere Parameter verwendet, zu initialisieren, schließen Sie jedes Parameterset wie im folgenden Beispiel gezeigt in Klammern ein.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein <xref:System.Collections.Generic.Dictionary%602> mit Instanzen vom Typ `StudentName` initialisiert.  
  
 [!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#34)]  
  
 Beachten Sie die zwei Paare geschweifter Klammern in jedem Element der Auflistung.  Die inneren Klammern schließen den Objektinitialisierer für `StudentName` ein, und die äußeren Klammern umfassen den Initialisierer für das Schlüssel\-Wert\-Paar, das dem `students` <xref:System.Collections.Generic.Dictionary%602> hinzugefügt wird.  Schließlich wird der ganze Auflistungsinitialisierer für das Wörterbuch in geschweifte Klammern eingeschlossen.  
  
## Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C\#\-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] erstellt wurde.  Dieses Projekt gilt standardmäßig für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 und hat einen Verweis auf System.Core.dll sowie eine using\-Direktive für System.Linq.  Wenn eine oder mehrere dieser Anforderungen im Projekt fehlen, können Sie sie manuell hinzufügen.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)