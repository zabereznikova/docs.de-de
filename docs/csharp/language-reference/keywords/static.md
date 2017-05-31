---
title: static (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: 36c9fd396914f2d958615b9f62666a0d0cc47fc1
ms.contentlocale: de-de
ms.lasthandoff: 05/15/2017

---
# <a name="static-c-reference"></a>static (C#-Referenz)
Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt. Der Modifizierer `static` kann mit Klassen, Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren verwendet werden, jedoch nicht mit Indexern, Finalizern oder Typen außer Klassen. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Die Deklaration einer Konstante oder eines Typs ist implizit ein statischer Member.  
  
 Ein statischer Member kann nicht über eine Instanz verwiesen werden. Stattdessen wird er über den Namen verwiesen. Betrachten Sie beispielsweise die folgende Klasse:  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Verwenden Sie zum Verweisen auf ein statischen Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem statischen Feld.  
  
 Es ist nicht möglich, [this](../../../csharp/language-reference/keywords/this.md) zum Verweis auf statische Methoden oder Eigenschaftenaccessoren zu verwenden.  
  
 Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse statisch sein.  
  
 Klassen und statische Klassen können über statische Konstruktoren verfügen. Statische Konstruktoren werden irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.  
  
> [!NOTE]
>  Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++. Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](https://docs.microsoft.com/cpp/cpp/storage-classes-cpp#static).
  
 Stellen Sie sich zur Veranschaulichung von statischen Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt. Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird. Sowohl die Methode als auch das Feld gehören nicht zu einem Instanzangestellten. Sie gehören stattdessen zur Unternehmensklasse. Daher sollten sie als statische Member der Klasse deklariert werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt. Der Einfachheit halber liest das Programm die aktuelle Anzahl von Angestellten von der Tastatur. Bei einer realen Anwendung sollten diese Informationen aus einer Datei gelesen werden.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, dass, obwohl Sie ein statisches Feld mit einem anderen noch nicht deklarierte, statischen Feld initialisieren können, die Ergebnisse undefiniert bleiben, bis Sie dem statischen Feld explizit einen Wert zuweisen.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

