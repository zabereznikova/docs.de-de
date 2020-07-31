---
title: Übergeben von Verweistypparametern – C#-Programmierhandbuch
description: Wenn Sie in C# einen Verweistypparameter als Wert übergeben, können sich die Daten in dem Objekt, auf das verwiesen wird, ändern, der Wert des Verweises selbst jedoch nicht.
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
ms.openlocfilehash: 64a4735eded7a468549862b3221b4fbd0966e64d
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864708"
---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>Übergeben von Verweistypparametern (C#-Programmierhandbuch)
Eine Variable eines [Verweistyps](../../language-reference/keywords/reference-types.md) enthält direkt keine Daten. Sie enthält einen Verweis auf die Daten. Wenn Sie einen Verweistypparameter nach Wert übergeben, ist es möglich, die Daten zu ändern, die zu dem Objekt gehören, auf das verwiesen wird, z.B. den Wert eines Klassenmembers. Sie können jedoch nicht den Wert des Verweises selbst ändern.Zum Beispiel. können Sie nicht mit dem gleichen Verweis eines neuen Objekts Arbeitsspeicher zuweisen und ihn außerhalb der Methode beibehalten. Dazu müssen Sie den Parameter mit den Schlüsselwörtern [ref](../../language-reference/keywords/ref.md) oder [out](../../language-reference/keywords/out-parameter-modifier.md) übergeben. Der Einfachheit halber wird im folgenden Beispiel `ref` verwendet.  
  
## <a name="passing-reference-types-by-value"></a>Übergeben von Verweistypen nach Wert  
 Im folgenden Beispiel wird gezeigt, wie Verweistypparameter, `arr`, nach Wert an eine Methode, `Change`, übergeben werden. Da der Parameter ein Verweis auf `arr` ist, ist es möglich, die Werte der Arrayelemente zu ändern. Der Versuch, den Parameter einem anderen Speicherort zuzuweisen, funktioniert aber nur innerhalb der Methode und wirkt sich nicht auf die ursprüngliche Variable `arr` aus.  
  
 [!code-csharp[csProgGuideParameters#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#7)]  
  
 Im vorherigen Beispiel, wurde das Verweistyp-Array `arr` ohne den `ref`-Parameter an die Methode übergeben. In diesem Fall wird eine Kopie des Verweises, die auf `arr` zeigt, an die Methode übergeben. Die Ausgabe zeigt, dass die Methode den Inhalt eines Arrayelements ändern kann, in diesem Fall von `1` in `888`. Durch das Zuweisen eines neuen Teils des Arbeitsspeichers mithilfe des Operators [new](../../language-reference/operators/new-operator.md) innerhalb der `Change`-Methode verweist die Variable `pArray` jedoch auf ein neues Array. Alle nachfolgenden Änderungen wirken sich daher nicht auf das ursprüngliche Array `arr` aus, das in `Main` erstellt wird. Tatsächlich werden in diesem Beispiel zwei Arrays erstellt, eines in der `Main`, und das andere in der `Change`-Methode.  
  
## <a name="passing-reference-types-by-reference"></a>Übergeben von Verweistypen nach Verweis  
 Das folgende Beispiel entspricht dem vorherigen, mit dem Unterschied, dass dem Methodenheader und -aufruf das `ref`-Schlüsselwort hinzugefügt wird. Alle Änderungen in der Methode haben Auswirkungen auf die ursprüngliche Variable im aufrufenden Programm.  
  
 [!code-csharp[csProgGuideParameters#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#8)]  
  
 Alle Änderungen innerhalb der Methode haben Auswirkungen auf das ursprüngliche Array in `Main`. Das ursprüngliche Array wird in der Tat mit dem `new`-Operator neu zugewiesen. Nach dem Aufruf der `Change`-Methode zeigt jeder Verweis auf `arr` auf die fünf Elemente umfassendes Array, das in der `Change`-Methode erstellt wird.  
  
## <a name="swapping-two-strings"></a>Austauschen von zwei Zeichenfolgen  
 Das Austauschen von Zeichenfolgen ist ein gutes Beispiel für das Übergeben von Verweistypparametern nach Verweis. Im Beispiel werden zwei Zeichenfolgen, `str1` und `str2`, in `Main` initialisiert und der `SwapStrings`-Methode als Parameter übergeben, die vom `ref`-Schlüsselwort geändert wurden. Die beiden Zeichenfolgen werden innerhalb der Methode und auch in `Main` ausgetauscht.  
  
 [!code-csharp[csProgGuideParameters#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#9)]  
  
 In diesem Beispiel müssen die Parameter nach Verweis übergeben werden, damit die Variablen im aufrufenden Programm beeinflusst werden. Wenn Sie das `ref`-Schlüsselwort aus dem Methodenheader und dem Methodenaufruf entfernen, erfolgen keine Änderungen im aufrufenden Programm.  
  
 Weitere Informationen zu Zeichenfolgen finden Sie unter [string](../../language-reference/builtin-types/reference-types.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Übergeben von Parametern](./passing-parameters.md)
- [ref](../../language-reference/keywords/ref.md)
- [in](../../language-reference/keywords/in-parameter-modifier.md)
- [out](../../language-reference/keywords/out.md)
- [Verweistypen](../../language-reference/keywords/reference-types.md)
