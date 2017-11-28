---
title: 'Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a>Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)
*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen. Wenn Sie Zeichenfolgenliterale oder –konstanten mit dem Operator `+` verketten, erstellt der Compiler eine einzelne Zeichenfolge. Es tritt keine Laufzeitverkettung auf. Zeichenfolgenvariablen können jedoch nur zur Laufzeit verkettet werden. In diesem Fall sollten Sie die Leistungsauswirkungen der verschiedenen Ansätze kennen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufgeteilt werden kann, um die Lesbarkeit im Quellcode zu verbessern. Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet. Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Laufzeitleistungseinbußen.  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Um Zeichenfolgenvariablen zu verketten, können Sie den Operator `+` bzw. `+=` oder die Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType>, oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden. Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet. Auch wenn Sie mehrere +-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert. Wenn Sie diesen Vorgang jedoch mehrfach wiederholen, z.B. in einer Schleife, kann dies Effizienzprobleme verursachen. Beachten Sie beispielsweise folgenden Code:  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge, konvertiert jedoch nicht den Wert der ursprünglichen NULL-Zeichenfolge.  
  
 Falls Sie keine große Anzahl an Zeichenfolgen (z.B. in einer Schleife) verketten, fallen die Leistungseinbußen dieses Codes wahrscheinlich nicht ins Gewicht. Dasselbe gilt für die Methoden <xref:System.String.Concat%2A?displayProperty=nameWithType> und <xref:System.String.Format%2A?displayProperty=nameWithType>.  
  
 Wenn jedoch die Leistung eine wichtige Rolle spielt, sollten Sie immer die Klasse <xref:System.Text.StringBuilder> zum Verketten von Zeichenfolgen verwenden. Im folgenden Code werden mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> Zeichenfolgen ohne den Verkettungseffekt des Operators `+` miteinander verkettet.  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)
