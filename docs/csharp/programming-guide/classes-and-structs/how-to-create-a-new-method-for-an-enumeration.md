---
title: "Gewusst wie: Erstellen einer neuen Methode f&#252;r eine Enumeration (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "enum-Erweiterbarkeit [C#]"
  - "Enumerationen [C#]"
  - "Erweiterungsmethoden [C#], Für Enumerationen"
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen einer neuen Methode f&#252;r eine Enumeration (C#-Programmierhandbuch)
Mit Erweiterungsmethoden können Sie Funktionen hinzufügen, die für einen bestimmten Enumerationstyp spezifisch sind.  
  
## Beispiel  
 Im folgenden Beispiel stellt die `Grades`\-Enumeration die möglichen Benotungen \(Buchstaben\) dar, die ein Student in einem Kurs erhalten kann.  Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`\-Typ hinzugefügt, mit dem jede Instanz dieses Typs angewiesen wird, ob der Student mit dieser Benotung den Kurs besteht.  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-create-a-new-meth_1.cs)]  
  
 Beachten Sie, dass die `Extensions`\-Klasse ebenfalls eine statische Variable enthält, die dynamisch aktualisiert wird und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert dieser Variable darstellt.  Dies zeigt, dass Erweiterungsmethoden im Hintergrund direkt für die statische Klasse aufgerufen werden, in der sie definiert sind.  
  
## Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie ihn, und fügen Sie ihn in ein Visual C\#\-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] erstellt wurde.  Dieses Projekt gilt standardmäßig für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 und hat einen Verweis auf System.Core.dll sowie eine `using`\-Direktive für System.Linq.  Wenn eine oder mehrere dieser Anforderungen im Projekt fehlen, können Sie sie manuell hinzufügen.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)