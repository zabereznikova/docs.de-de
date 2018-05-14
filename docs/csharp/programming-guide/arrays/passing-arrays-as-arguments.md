---
title: Übergeben von Arrays als Argumente (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Übergeben von Arrays als Argumente (C#-Programmierhandbuch)
Arrays können als Argumente an Methodenparameter übergeben werden. Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>Übergeben von eindimensionalen Arrays als Argumente  
 Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben. Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>description  
 Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `PrintArray`-Methode für Zeichenfolgen übergeben. Die Methode zeigt die Elemente des Arrays an. Als Nächstes werden die Methoden `ChangeArray` und `ChangeArrayElement` aufgerufen, um zu veranschaulichen, dass das Senden eines Arrayarguments nach Wert keine Änderungen an den Arrayelementen verhindert.  
  
### <a name="code"></a>Code  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>Übergeben von mehrdimensionalen Arrays als Argumente  
 Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>description  
 Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben. Die Methode zeigt die Elemente des Arrays an.  
  
### <a name="code"></a>Code  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)
