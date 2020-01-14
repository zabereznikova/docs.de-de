---
title: Übergeben von Arrays als Argumente – C#-Programmierhandbuch
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705690"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Übergeben von Arrays als Argumente (C#-Programmierhandbuch)

Arrays können als Argumente an Methodenparameter übergeben werden. Da es sich bei Arrays um Verweistypen handelt, kann die Methode den Wert der Elemente ändern.

## <a name="passing-single-dimensional-arrays-as-arguments"></a>Übergeben von eindimensionalen Arrays als Argumente

Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben. Die folgende Anweisung sendet z.B. ein Array an eine print-Methode.

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

Im folgenden Code wird eine partielle Implementierung der print-Methode veranschaulicht.

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

Sie können einen neuen Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Array von Zeichenfolgen initialisiert und als Argument an eine `DisplayArray`-Methode für Zeichenfolgen übergeben. Die Methode zeigt die Elemente des Arrays an. Als Nächstes kehrt die `ChangeArray`-Methode die Elemente des Arrays um, und die `ChangeArrayElements`-Methode ändert die ersten drei Elemente des Arrays. Nachdem jede Methode zurückgegeben wird, zeigt die `DisplayArray`-Methode an, dass das Übergeben eines Arrays nach Wert keine Änderungen an den Arrayelementen verhindert.

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a>Übergeben von mehrdimensionalen Arrays als Argumente

Sie können ein initialisiertes mehrdimensionales Array genauso wie Sie ein eindimensionales Array an eine Methode übergeben.

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

Der folgende Code zeigt eine partielle Deklaration einer print-Methode, die ein zweidimensionales Array als Argument akzeptiert.

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

Wie im folgenden Beispiel dargestellt können Sie ein Array in einem Schritt initialisieren und übergeben.

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein zweidimensionales Array von ganzen Zahlen initialisiert und an die `Print2DArray`-Methode übergeben. Die Methode zeigt die Elemente des Arrays an.

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Arrays](index.md)
- [Eindimensionale Arrays](single-dimensional-arrays.md)
- [Mehrdimensionale Arrays](multidimensional-arrays.md)
- [Verzweigte Arrays](jagged-arrays.md)
