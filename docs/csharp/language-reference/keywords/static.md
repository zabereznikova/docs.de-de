---
title: "static (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "static"
  - "static_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "static-Schlüsselwort [C#]"
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# static (C#-Referenz)
Mit dem `static`\-Modifizierer kann ein statischer Member deklariert werden, der zum Typ selbst und nicht zu einem bestimmten Objekt gehört.  Der `static`\-Modifizierer kann bei Klassen, Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren verwendet werden, jedoch nicht bei Indexern, Destruktoren oder Typen, die keine Klassen sind.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Beispiel  
 Die folgende Klasse ist zum Beispiel als `static` deklariert und enthält nur `static`\-Methoden:  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Eine Konstanten\- oder Typdeklaration stellt implizit einen Member des Typs **static** dar.  
  
 Auf einen Member vom Typ **static** darf nicht über eine Instanz verwiesen werden.  Stattdessen geschieht dies über den Typnamen.  Betrachten Sie z. B. die folgende Klasse:  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Verwenden Sie zum Verweisen auf den statischen Member `x` den vollqualifizierten Namen \(`MyBaseC.MyStruct.x`\), sofern nicht vom selben Projektumfang auf den Member zugegriffen werden kann:  
  
```c#  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Während die Instanz einer Klasse eine separate Kopie aller Instanzenfelder der Klasse enthält, ist lediglich eine Kopie jedes statischen Felds vorhanden.  
  
 [this](../../../csharp/language-reference/keywords/this.md) kann nicht zum Verweisen auf statische Methoden oder Eigenschaftenaccessoren verwendet werden.  
  
 Wenn das `static`\-Schlüsselwort auf eine Klasse angewendet wird, müssen alle Member der Klasse statisch sein.  
  
 Klassen und statische Klassen können möglicherweise über statische Konstruktoren verfügen.  Statische Konstruktoren werden irgendwann zwischen dem Programmstart und der Klasseninstanziierung aufgerufen.  
  
> [!NOTE]
>  Die Verwendung des `static`\-Schlüsselworts ist eingeschränkter als in C\+\+.  Einen Vergleich mit dem C\+\+\-Schlüsselwort finden Sie unter [Statisch](/visual-cpp/misc/static-cpp).  
  
 Betrachten Sie zur Demonstration von statischen Membern eine Klasse, die einen Firmenangestellten repräsentiert.  Nehmen Sie an, dass die Klasse eine Methode zum Zählen der Angestellten und ein Feld zum Speichern der Angestelltenzahl enthält.  Weder die Methode noch das Feld sind Elemente einer Angestellteninstanz.  Stattdessen gehören sie zur Klasse.  Daher sollten sie als Member des Typs **static** der Klasse deklariert werden.  
  
## Beispiel  
 In diesem Beispiel werden der Name und die ID eines neuen Angestellten eingelesen, der Angestelltenzähler wird um eins erhöht, und die Informationen für den neuen Angestellten sowie die neue Angestelltenzahl werden angezeigt.  Der Einfachheit halber wird bei diesem Beispiel die Angestelltenzahl über die Tastatur eingegeben.  In einer realen Anwendung sollten diese Informationen jedoch aus einer Datei eingelesen werden.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## Beispiel  
 Dieses Beispiel zeigt, dass es zwar möglich ist, ein statisches Feld mit einem anderen statischen, noch nicht deklarierten Feld zu initialisieren, dass die Ergebnisse jedoch undefiniert bleiben, solange dem statischen Feld nicht explizit ein Wert zugewiesen wird.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)