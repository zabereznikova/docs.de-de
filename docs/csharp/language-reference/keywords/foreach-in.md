---
title: foreach, in (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
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
ms.sourcegitcommit: 81117b1419c2a9c3babd6a7429052e2b23e08a70
ms.openlocfilehash: 1c873dfdf001f7efc3340637d210e5fdf42a2852
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="foreach-in-c-reference"></a>foreach, in (C#-Referenz)
Mit der `foreach`-Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt, das die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert. Die `foreach`-Anweisung wird verwendet, um die Auflistung zu durchlaufen und dadurch die gewünschten Informationen zu erhalten. Setzen Sie sie nicht ein, um der Auflistung Elemente hinzuzufügen oder aus ihr zu entfernen, um unvorhersehbare Nebeneffekte zu vermeiden. Wenn Sie Elemente zu der Quellauflistung hinzufügen oder daraus entfernen müssen, verwenden Sie eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife.  
  
 Die Ausführung der eingebetteten Anweisungen wird für jedes Element in dem Array oder der Auflistung fortgesetzt. Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `foreach`-Block folgt, übergeben.  
  
 Sie können die Schleife an jedem Punkt im `foreach`-Block mit dem Schlüsselwort [break](../../../csharp/language-reference/keywords/break.md) unterbrechen oder mit dem Schlüsselwort [continue](../../../csharp/language-reference/keywords/continue.md) direkt zum nächsten Durchlauf der Schleife springen.  
  
 Eine `foreach`-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.  
  
 Weitere Informationen zum `foreach`-Schlüsselwort und zu Codebeispielen finden Sie unter den folgenden Themen:  
  
 [Verwenden von foreach mit Arrays](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [Gewusst wie: Zugreifen auf Sammlungsklassen mit foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt drei Beispiele:  
  
-   eine typische `foreach`-Schleife, die den Inhalt eines Arrays von Ganzzahlen anzeigt  
  
-   eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife, die die gleiche Aufgabe ausführt  
  
-   eine `foreach`-Schleife, die die Anzahl von Elementen im Array enthält  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)   
 [for](../../../csharp/language-reference/keywords/for.md)

