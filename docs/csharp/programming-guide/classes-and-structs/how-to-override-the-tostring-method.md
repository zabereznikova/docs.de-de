---
title: "Gewusst wie: &#220;berschreiben der ToString-Methode (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Vererbung [C#], Überschreiben von OnPaint und ToString"
  - "ToString-Methode, Überschreiben in C#"
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Gewusst wie: &#220;berschreiben der ToString-Methode (C#-Programmierhandbuch)
Alle Klassen oder Strukturen in C\# erben implizit die <xref:System.Object>\-Klasse.  Alle Objekte in C\# rufen daher die <xref:System.Object.ToString%2A>\-Methode ab, die eine Zeichenfolgendarstellung des Objekts zurückgibt.  Zum Beispiel verfügen alle Variablen des `int`\-Typs über eine `ToString`\-Methode, mit der ihr Inhalt als Zeichenfolge zurückgegeben werden kann:  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Wenn Sie eine benutzerdefinierte Klasse oder Struktur erstellen, sollten Sie die <xref:System.Object.ToString%2A>\-Methode überschreiben, um dem Clientcode Informationen über den Typ bereitzustellen.  
  
 Weitere Informationen zum Erstellen von Formatzeichenfolgen und andere Typen benutzerdefinierter Formatierung mit der `ToString`\-Methode finden Sie unter veranschaulicht [Formatierung von Typen](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
> [!IMPORTANT]
>  Bei der Entscheidung, welche Informationen über diese Methode bereitgestellt werden, sollten Sie berücksichtigen, ob die Klasse oder Struktur möglicherweise einmal von nicht vertrauenswürdigem Code verwendet wird.  Stellen Sie keine Informationen bereit, die von bösartigem Code genutzt werden könnten.  
  
### So überschreiben Sie die ToString\-Methode in der Klasse oder Struktur  
  
1.  Deklarieren Sie eine `ToString`\-Methode mit den folgenden Modifizierern und folgendem Rückgabetyp:  
  
    ```c#  
    public override string ToString(){}  
    ```  
  
2.  Implementieren Sie die Methode, sodass sie eine Zeichenfolge zurückgibt.  
  
     Das folgende Codebeispiel gibt nicht nur den Namen der Klasse zurück, sondern auch die Daten für eine bestimmte Instanz der Klasse.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Im folgenden Codebeispiel wird die Verwendung der `ToString`\-Methode veranschaulicht.  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## Siehe auch  
 <xref:System.IFormattable>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [neu](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [Virtuell](../../../csharp/language-reference/keywords/virtual.md)   
 [Formatierung von Typen](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)