---
title: "sealed (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sealed"
  - "sealed_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sealed-Schlüsselwort [C#]"
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# sealed (C#-Referenz)
Wenn der `sealed`\-Modifizierer auf eine Klasse angewendet wird, verhindert er, dass andere Klassen von dieser Klasse erben.  Im folgenden Beispiel erbt die Klasse `B` von der Klasse `A`, es kann jedoch keine Klasse von der Klasse `B` erben.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 Sie können den `sealed`\-Modifizierer auch auf eine Methode oder Eigenschaft anwenden, die eine virtuelle Methode oder Eigenschaft in einer Basisklasse überschreibt.  Auf diese Weise ermöglichen Sie, dass Klassen von Ihrer Klasse erben, und verhindern, dass sie bestimmte virtuelle Methoden oder Eigenschaften überschreiben.  
  
## Beispiel  
 Im folgenden Beispiel erbt `Z` von `Y`, `Z` kann jedoch nicht die virtuelle Funktion `F` überschreiben, die in `X` deklariert und in `Y` versiegelt wird.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 Wenn Sie neue Methoden oder Eigenschaften in einer Klasse definieren, können Sie verhindern, dass diese durch abgeleitete Klassen überschrieben werden, indem Sie sie nicht als [virtual](../../../csharp/language-reference/keywords/virtual.md) deklarieren.  
  
 Verwenden Sie den [abstract](../../../csharp/language-reference/keywords/abstract.md)\-Modifizierer nicht mit einer versiegelten Klasse, da eine abstrakte Klasse von einer Klasse geerbt werden muss, die eine Implementierung der abstrakten Methoden oder Eigenschaften bereitstellt.  
  
 Wenn der `sealed`\-Modifizierer auf eine Methode oder eine Eigenschaft angewendet wird, muss er stets mit [override](../../../csharp/language-reference/keywords/override.md) verwendet werden.  
  
 Strukturen sind implizit versiegelt und können deshalb nicht geerbt werden.  
  
 Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Weitere Beispiele finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## Beispiel  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 Im voranstehenden Beispiel können Sie versuchen, von der versiegelten Klasse zu erben, indem Sie folgende Anweisung verwenden:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 Das Ergebnis ist eine Fehlermeldung:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Hinweise  
 Um zu ermitteln, ob eine Klasse, Methode oder Eigenschaft versiegelt werden soll, beachten Sie die folgenden beiden Punkte:  
  
-   Die möglichen Vorteile für abgeleitete Klassen durch die Möglichkeit, Ihre Klasse anzupassen  
  
-   Die Möglichkeit, dass abgeleitete Klassen Ihre Klassen in einer Weise ändern können, dass diese nicht mehr korrekt funktionieren  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [Virtuell](../../../csharp/language-reference/keywords/virtual.md)