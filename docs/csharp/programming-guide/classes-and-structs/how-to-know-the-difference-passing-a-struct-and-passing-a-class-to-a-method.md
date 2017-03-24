---
title: "Gewusst wie: Unterschiede zwischen dem &#220;bergeben einer Struktur und dem &#220;bergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Methoden [C#], Übergeben von Klassen im Vergleich zum Übergeben von Strukturen"
  - "Übergeben von Parametern (C#), Strukturen im Vergleich zu Klassen"
  - "Strukturen [C#], Übergeben als Methodenparameter"
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# Gewusst wie: Unterschiede zwischen dem &#220;bergeben einer Struktur und dem &#220;bergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch)
Im folgenden Beispiel wird veranschaulicht, wie die Übergabe von [Struktur](../../../csharp/language-reference/keywords/struct.md) einer Methode aus dem Übergeben einer [Klasse](../../../csharp/language-reference/keywords/class.md)\-Instanz einer Methode unterscheidet.  Im Beispiel werden beide Argumente \(Struktur\) und Klasseninstanz als Wert und beide Methoden ändern den Wert aus einem Feld des Arguments übergeben.  Allerdings sind die Ergebnisse der beiden Methoden nicht identisch, da die übergebene übergeben, wenn Sie eine Struktur unterscheidet, die übergeben wird, wenn Sie eine Instanz einer Klasse übergeben.  
  
 Da eine Struktur [Werttyp](../../../csharp/language-reference/keywords/value-types.md)ist, wenn Sie [Ausführen einer Struktur durch einen Wert](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) auf eine Methode, die Methode eine Kopie der Struktur arguments empfangen und ausgeführt werden.  Die Methode verfügt über keinen Zugriff auf die ursprüngliche Struktur in der aufrufenden Methode und kann daher in jeder Hinsicht ändern.  Die Methode kann nur die Kopie ändern.  
  
 Eine Instanz einer Klasse, [Verweistyp](../../../csharp/language-reference/keywords/reference-types.md)ist kein Werttyp.  Wenn [ein Referenztyp durch einen Wert übergeben wird](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) auf eine Methode, die Methode eine Kopie des Verweises auf die Klasseninstanz empfängt.  Das heißt, erhält die Methode eine Kopie der Adresse der Instanz keine Kopie der Instanz selbst.  Die Klasseninstanz in der aufrufenden Methode verfügt über eine Adresse, hat der Parameter an die aufgerufene Methode eine Kopie der Adresse und beide dasselbe Objekt verweisen auf Adressen an.  Da der Parameter nur eine Kopie der Adresse enthält, kann die aufgerufene Methode die Adresse der Klasseninstanz in der aufrufenden Methode nicht ändern.  Allerdings kann die aufgerufene Methode die Adresse verwenden, um die Klassenmember zuzugreifen, die sowohl die ursprüngliche Adresse und die Kopie verweisen.  Wenn die aufgerufene Methode einen Klassenmember ändert, ändert die ursprüngliche Klasseninstanz in der aufrufenden Methode.  
  
 Die Ausgabe des folgenden Beispiels veranschaulicht den Unterschied.  Der Wert des Felds `willIChange` der Klasseninstanz wird durch den Aufruf der Methode `ClassTaker` geändert, da die Methode die Adresse im Parameter verwendet wird, um das angegebene Feld der Klasseninstanz zu suchen.  Das `willIChange` Feld der Struktur in der aufrufenden Methode wird nicht durch den Aufruf der Methode `StructTaker` , da der Wert des Arguments eine Kopie der Struktur selbst ist keine Kopie der Adresse geändert.  `StructTaker` ändert die Kopie und die Kopie geht verloren, wenn durch Aufruf von `StructTaker` abgeschlossen ist.  
  
## Beispiel  
 [!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)