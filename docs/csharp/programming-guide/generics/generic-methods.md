---
title: Generische Methoden (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a>Generische Methoden (C#-Programmierhandbuch)
Bei einer generischen Methode handelt es sich um eine mit Typparametern deklarierte Methode, wie folgt:  
  
 [!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]  
  
 Im folgenden Codebeispiel wird eine Möglichkeit gezeigt, die Methode mit `int` für das Typargument aufzurufen:  
  
 [!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]  
  
 Sie können das Typargument auch weglassen, dann wird es vom Compiler abgeleitet. Der folgende Aufruf von `Swap` bewirkt das gleiche wie der vorherige Aufruf:  
  
 [!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]  
  
 Für statische Methoden und Instanzmethoden gelten die gleichen Typrückschlussregeln. Der Compiler kann Typparameter auf der Grundlage der übergebenen Methodenargumente ableiten. Eine Einschränkung oder ein Rückgabewert genügen ihm zur Ableitung des Typparameters nicht. Infolgedessen ist ein Typrückschluss bei Methoden ohne Parameter nicht möglich. Der Typrückschluss tritt beim Kompilieren auf, bevor der Compiler versucht, die Signaturen von überladenen Methoden aufzulösen. Der Compiler wendet Typrückschlusslogik auf alle generischen Methoden gleichen Namens an. Im Schritt zur Überladungsauflösung schließt der Compiler nur die generischen Methoden ein, bei denen der Typrückschluss erfolgreich war.  
  
 Innerhalb einer generischen Klasse können nicht generische Methoden die Typparameter auf Klassenebene folgendermaßen zugreifen:  
  
 [!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]  
  
 Wenn eine generische Methode definiert wird, die die gleichen Typparameter wie die übergeordnete Klasse verwendet, gibt der Compiler die Warnung CS0693 aus, weil innerhalb des Gültigkeitsbereichs der Methode das Argument für das äußere `T` durch das Argument für das innere `T` ausgeblendet wird. Falls Sie die Flexibilität benötigen, eine generische Klassenmethode mit anderen als den bei der Instanziierung der Klasse bereitgestellten Typargumenten aufrufen zu können, sollten Sie einen anderen Bezeichner für den Typparameter der Methode erwägen, wie in `GenericList2<T>` im folgenden Beispiel dargestellt.  
  
 [!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]  
  
 Verwenden Sie Einschränkungen, um spezialisiertere Operationen bei Typparametern in Methoden zu ermöglichen. Die Version von `Swap<T>`, jetzt `SwapIfGreater<T>` genannt, kann nur mit Typargumenten verwendet werden, die <xref:System.IComparable%601> implementieren.  
  
 [!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]  
  
 Generische Methoden können auf mehrere Typparameter überladen werden. Beispielsweise können sich folgende Methoden alle in derselben Klasse befinden:  
  
 [!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)

