---
title: "unsafe (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "unsafe_CSharpKeyword"
  - "unsafe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unsafe-Schlüsselwort [C#]"
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# unsafe (C#-Referenz)
Das `unsafe`\-Schlüsselwort deutet auf einen nicht sicheren Kontext hin, der für alle Zeigeroperationen erforderlich ist.  Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Sie können den `unsafe`\-Modifizierer in der Deklaration eines Typs oder Members verwenden.  Daraufhin wird der gesamte Text des Typs oder Members als nicht sicherer Kontext betrachtet.  Das folgende Beispiel enthält beispielsweise eine Methode, die mit dem `unsafe`\-Modifizierer deklariert wurde:  
  
```  
  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Der Gültigkeitsbereich des nicht sicheren Kontexts reicht von der Parameterliste bis zum Methodenende, sodass auch in der Parameterliste Zeiger verwendet werden können:  
  
```  
  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 Sie können auch einen nicht sicheren Block verwenden, um die Verwendung unsicheren Codes innerhalb dieses Blocks zu ermöglichen.  Beispiele:  
  
```  
  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Zum Kompilieren von unsicherem Code muss die [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)\-Compileroption angegeben werden.  Unsicherer Code kann nicht durch die Common Language Runtime überprüft werden.  
  
## Beispiel  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Puffer fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)