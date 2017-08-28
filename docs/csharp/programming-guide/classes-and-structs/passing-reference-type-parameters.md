---
title: "Übergeben von Verweistypparametern (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>Übergeben von Verweistypparametern (C#-Programmierhandbuch)
Eine Variable eines [Verweistyps](../../../csharp/language-reference/keywords/reference-types.md) enthält direkt keine Daten. Sie enthält einen Verweis auf die Daten. Wenn Sie einen Verweistypparameter nach Wert übergeben, ist es möglich, die Daten zu ändern, auf die die Daten zeigen, z.B. den Wert eines Klassenmembers. Sie können jedoch nicht den Wert des Verweises selbst ändern. Das bedeutet, dass Sie nicht mit dem gleichen Verweis einer neuen Klasse Arbeitsspeicher zuweisen und ihn außerhalb des Blocks beibehalten können. Dazu müssen Sie den Parameter mit den Schlüsselwörtern [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out.md) übergeben. Der Einfachheit halber wird im folgenden Beispiel `ref` verwendet.  
  
## <a name="passing-reference-types-by-value"></a>Übergeben von Verweistypen nach Wert  
 Im folgenden Beispiel wird gezeigt, wie Verweistypparameter, `arr`, nach Wert an eine Methode, `Change`, übergeben werden. Da der Parameter ein Verweis auf `arr` ist, ist es möglich, die Werte der Arrayelemente zu ändern. Der Versuch, den Parameter einem anderen Speicherort zuzuweisen, funktioniert aber nur innerhalb der Methode und wirkt sich nicht auf die ursprüngliche Variable `arr` aus.  
  
 [!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 Im vorherigen Beispiel, wurde das Verweistyp-Array `arr` ohne den `ref`-Parameter an die Methode übergeben. In diesem Fall wird eine Kopie des Verweises, die auf `arr` zeigt, an die Methode übergeben. Die Ausgabe zeigt, dass die Methode den Inhalt eines Arrayelements ändern kann, in diesem Fall von `1` in `888`. Durch das Zuweisen eines neuen Teils des Arbeitsspeichers mithilfe des Operators [new](../../../csharp/language-reference/keywords/new.md) innerhalb der `Change`-Methode verweist die Variable `pArray` jedoch auf ein neues Array. Alle nachfolgenden Änderungen wirken sich daher nicht auf das ursprüngliche Array `arr` aus, das in `Main` erstellt wird. Tatsächlich werden in diesem Beispiel zwei Arrays erstellt, eines in der `Main`, und das andere in der `Change`-Methode.  
  
## <a name="passing-reference-types-by-reference"></a>Übergeben von Verweistypen nach Verweis  
 Das folgende Beispiel entspricht dem vorherigen, mit dem Unterschied, dass dem Methodenheader und -aufruf das `ref`-Schlüsselwort hinzugefügt wird. Alle Änderungen in der Methode haben Auswirkungen auf die ursprüngliche Variable im aufrufenden Programm.  
  
 [!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 Alle Änderungen innerhalb der Methode haben Auswirkungen auf das ursprüngliche Array in `Main`. Das ursprüngliche Array wird in der Tat mit dem `new`-Operator neu zugewiesen. Nach dem Aufruf der `Change`-Methode zeigt jeder Verweis auf `arr` auf die fünf Elemente umfassendes Array, das in der `Change`-Methode erstellt wird.  
  
## <a name="swapping-two-strings"></a>Austauschen von zwei Zeichenfolgen  
 Das Austauschen von Zeichenfolgen ist ein gutes Beispiel für das Übergeben von Verweistypparametern nach Verweis. Im Beispiel werden zwei Zeichenfolgen, `str1` und `str2`, in `Main` initialisiert und der `SwapStrings`-Methode als Parameter übergeben, die vom `ref`-Schlüsselwort geändert wurden. Die beiden Zeichenfolgen werden innerhalb der Methode und auch in `Main` ausgetauscht.  
  
 [!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 In diesem Beispiel müssen die Parameter nach Verweis übergeben werden, damit die Variablen im aufrufenden Programm beeinflusst werden. Wenn Sie das `ref`-Schlüsselwort aus dem Methodenheader und dem Methodenaufruf entfernen, erfolgen keine Änderungen im aufrufenden Programm.  
  
 Weitere Informationen zu Zeichenfolgen finden Sie unter [string](../../../csharp/language-reference/keywords/string.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Übergeben von Arrays mithilfe von „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)

